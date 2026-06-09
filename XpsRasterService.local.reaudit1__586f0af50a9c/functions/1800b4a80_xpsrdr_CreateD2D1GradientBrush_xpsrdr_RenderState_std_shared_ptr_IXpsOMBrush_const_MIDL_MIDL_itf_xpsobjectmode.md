# xpsrdr::CreateD2D1GradientBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0014 const &,float *)

- ea: `0x1800b4a80`
- end: `0x1800b5358`
- name: `?CreateD2D1GradientBrush@xpsrdr@@YA?AV?$shared_ptr@UID2D1Brush@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMBrush@@@3@AEBW4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0014@@PEAM@Z`
- size: `2264`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800b3ecc`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a8c1c`
- `0x1800b20e8`
- `0x1800b2154`
- `0x1800b39f4`
- `0x1800b4a80`
- `0x1800b5748`
- `0x1800b9aec`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
std::_Ref_count_base **__fastcall xpsrdr::CreateD2D1GradientBrush(
        std::_Ref_count_base **a1,
        std::_Ref_count_base *a2,
        _QWORD **a3,
        _DWORD *a4,
        std::_Ref_count_base *a5)
{
  __int64 (__fastcall ***v7)(_QWORD, GUID *, std::_Ref_count_base **); // rcx
  __int64 (__fastcall **v8)(_QWORD, GUID *, std::_Ref_count_base **); // rax
  int v9; // ebx
  int v10; // edx
  const char *v11; // r8
  int v12; // r9d
  int v13; // eax
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  __int64 v17; // rax
  int v18; // ebx
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  float v22; // xmm6_4
  int v23; // eax
  int v24; // edx
  const char *v25; // r8
  int v26; // r9d
  int v27; // eax
  const char *v28; // rdx
  const char *v29; // r8
  int v30; // r9d
  int v31; // r15d
  int v32; // eax
  const char *v33; // rdx
  const char *v34; // r8
  int v35; // r9d
  unsigned int v36; // r12d
  __int64 v37; // rax
  int v38; // ebx
  int v39; // edx
  const char *v40; // r8
  int v41; // r9d
  int v42; // eax
  int v43; // edx
  const char *v44; // r8
  int v45; // r9d
  unsigned __int64 i; // rbx
  __int64 v47; // rax
  int v48; // edi
  int v49; // edx
  const char *v50; // r8
  int v51; // r9d
  int v52; // eax
  int v53; // edx
  const char *v54; // r8
  int v55; // r9d
  __int64 v56; // rax
  int v57; // edi
  int v58; // edx
  const char *v59; // r8
  int v60; // r9d
  const __m128i *D2D1Color; // rax
  std::_Ref_count_base *v62; // r14
  __int64 **RenderTargetStackTop; // rax
  __int64 *v64; // rcx
  __int64 v65; // rax
  unsigned int v66; // r10d
  int v67; // ebx
  const char *v68; // rdx
  const char *v69; // r8
  int v70; // r9d
  __int64 (__fastcall **v71)(std::_Ref_count_base *, GUID *, _OWORD *); // rax
  int v72; // ebx
  int v73; // edx
  const char *v74; // r8
  int v75; // r9d
  int v76; // eax
  int v77; // edx
  const char *v78; // r8
  int v79; // r9d
  int v80; // eax
  int v81; // edx
  const char *v82; // r8
  int v83; // r9d
  int v84; // eax
  int v85; // edx
  const char *v86; // r8
  int v87; // r9d
  __int64 **v88; // rax
  __int64 *v89; // rcx
  __int64 v90; // rax
  int v91; // ebx
  int v92; // edx
  const char *v93; // r8
  int v94; // r9d
  std::_Ref_count_base *v95; // rcx
  __int64 (__fastcall **v96)(std::_Ref_count_base *, GUID *, _OWORD *); // rax
  int v97; // ebx
  int v98; // edx
  const char *v99; // r8
  int v100; // r9d
  int v101; // eax
  int v102; // edx
  const char *v103; // r8
  int v104; // r9d
  int v105; // eax
  int v106; // edx
  const char *v107; // r8
  int v108; // r9d
  __int64 **v109; // rax
  __int64 *v110; // rcx
  __int64 v111; // rax
  int v112; // ebx
  int v113; // edx
  const char *v114; // r8
  int v115; // r9d
  xpsrdr *v117; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v118; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v119; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v120; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v121[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v122; // [rsp+70h] [rbp-90h] BYREF
  int v123; // [rsp+74h] [rbp-8Ch] BYREF
  std::_Ref_count_base *v124[2]; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v125[2]; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v126[2]; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v127[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v128; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v129; // [rsp+C8h] [rbp-38h]
  std::_Ref_count_base *v130[2]; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v131; // [rsp+E8h] [rbp-18h] BYREF
  xpsrdr **v132; // [rsp+F0h] [rbp-10h]
  std::_Ref_count_base **v133; // [rsp+F8h] [rbp-8h]
  std::_Ref_count_base *v134[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v135; // [rsp+110h] [rbp+10h]
  _OWORD v136[3]; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v137[2]; // [rsp+148h] [rbp+48h] BYREF

  v119 = a2;
  v118 = a5;
  *(_OWORD *)v125 = 0;
  LODWORD(v117) = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, std::_Ref_count_base **))*a3;
  v8 = (__int64 (__fastcall **)(_QWORD, GUID *, std::_Ref_count_base **))**a3;
  v131 = 0;
  v132 = &v117;
  v133 = v125;
  v9 = (*v8)(v7, &GUID_edb59622_61a2_42c3_bace_acf2286c06bf, &v131);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v131);
  if ( (int)v117 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v117, v10, v11, v12);
  if ( v9 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v9, v10, v11, v12);
  memset(v137, 0, 28);
  v13 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _OWORD *))(*(_QWORD *)v125[0] + 40LL))(v125[0], v137);
  if ( v13 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
  *(_OWORD *)v130 = 0;
  LODWORD(v117) = 0;
  v17 = *(_QWORD *)v125[0];
  v131 = 0;
  v132 = &v117;
  v133 = v130;
  v18 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v17 + 64))(v125[0], &v131);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v131);
  if ( (int)v117 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v117, v19, v20, v21);
  if ( v18 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
  v22 = 0.0;
  if ( v130[0] )
  {
    *(_OWORD *)v134 = 0;
    v135 = 0;
    v23 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v130[0] + 40LL))(
            v130[0],
            v134);
    if ( v23 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v23, v24, v25, v26);
    *(_OWORD *)((char *)v137 + 4) = *(_OWORD *)v134;
    *(_QWORD *)((char *)&v137[1] + 4) = v135;
  }
  else
  {
    *(__m128i *)((char *)v137 + 4) = _mm_load_si128((const __m128i *)&_xmm);
    *(_QWORD *)((char *)&v137[1] + 4) = 0;
  }
  v122 = 0;
  v27 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *))(*(_QWORD *)v125[0] + 104LL))(v125[0], &v122);
  if ( v27 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v27, (int)v28, v29, v30);
  switch ( v122 )
  {
    case 1:
      v31 = 0;
      break;
    case 2:
      v31 = 2;
      break;
    case 3:
      v31 = 1;
      break;
    default:
      xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(v122 - 2), v28, (int)v29);
  }
  v123 = 0;
  v32 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *))(*(_QWORD *)v125[0] + 120LL))(v125[0], &v123);
  if ( v32 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v32, (int)v33, v34, v35);
  if ( v123 == 1 )
  {
    v36 = 1;
  }
  else
  {
    if ( v123 != 2 )
      xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(v123 - 1), v33, (int)v34);
    v36 = 0;
  }
  *(_OWORD *)v127 = 0;
  LODWORD(v117) = 0;
  v37 = *(_QWORD *)v125[0];
  v131 = 0;
  v132 = &v117;
  v133 = v127;
  v38 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v37 + 56))(v125[0], &v131);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v131);
  if ( (int)v117 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v117, v39, v40, v41);
  if ( v38 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v38, v39, v40, v41);
  v120 = 0;
  v42 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, unsigned int *))(*(_QWORD *)v127[0] + 24LL))(v127[0], &v120);
  if ( v42 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v42, v43, v44, v45);
  v128 = 0;
  v129 = 0;
  std::vector<D2D1_GRADIENT_STOP>::_Construct_n<>(&v128, v120);
  for ( i = 0; i < v120; ++i )
  {
    *(_OWORD *)v121 = 0;
    LODWORD(v117) = 0;
    v47 = *(_QWORD *)v127[0];
    v131 = 0;
    v132 = &v117;
    v133 = v121;
    v48 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, std::_Ref_count_base **))(v47 + 32))(
            v127[0],
            (unsigned int)i,
            &v131);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v131);
    if ( (int)v117 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v117, v49, v50, v51);
    if ( v48 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v48, v49, v50, v51);
    v52 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, unsigned __int64))(*(_QWORD *)v121[0] + 32LL))(
            v121[0],
            v128 + 20 * i);
    if ( v52 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v52, v53, v54, v55);
    memset(v136, 0, 44);
    *(_OWORD *)v134 = 0;
    LODWORD(v117) = 0;
    v56 = *(_QWORD *)v121[0];
    v131 = 0;
    v132 = &v117;
    v133 = v134;
    v57 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _OWORD *, std::_Ref_count_base **))(v56 + 48))(
            v121[0],
            v136,
            &v131);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v131);
    if ( (int)v117 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v117, v58, v59, v60);
    if ( v57 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v57, v58, v59, v60);
    D2D1Color = (const __m128i *)xpsrdr::GetD2D1Color(v124, v119, v136, v134);
    *(__m128i *)(v128 + 20 * i + 4) = _mm_loadu_si128(D2D1Color);
    v22 = v22 + (float)(*(float *)v137 * *(float *)(v128 + 20 * i + 16));
    if ( v134[1] )
      std::_Ref_count_base::_Decref(v134[1]);
    if ( v121[1] )
      std::_Ref_count_base::_Decref(v121[1]);
  }
  if ( v118 && v120 )
    *(float *)v118 = v22 / (float)(int)v120;
  *(_OWORD *)v126 = 0;
  LODWORD(v117) = 0;
  v62 = v119;
  RenderTargetStackTop = (__int64 **)xpsrdr::RenderState::GetRenderTargetStackTop(v119);
  v64 = *RenderTargetStackTop;
  v65 = **RenderTargetStackTop;
  v131 = 0;
  v132 = &v117;
  v133 = v126;
  v67 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, int, std::_Ref_count_base **))(v65 + 72))(
          v64,
          v128,
          v66,
          v36,
          v31,
          &v131);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v131);
  if ( (int)v117 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v117, (int)v68, v69, v70);
  if ( v67 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v67, (int)v68, v69, v70);
  if ( *a4 == 8 )
  {
    ++*(_DWORD *)(*((_QWORD *)v62 + 68) + 48LL);
    *(_OWORD *)v124 = 0;
    LODWORD(v117) = 0;
    v96 = *(__int64 (__fastcall ***)(std::_Ref_count_base *, GUID *, _OWORD *))v125[0];
    *(_QWORD *)&v136[0] = 0;
    *((_QWORD *)&v136[0] + 1) = &v117;
    *(_QWORD *)&v136[1] = v124;
    v97 = (*v96)(v125[0], &GUID_005e279f_c30d_40ff_93ec_1950d3c528db, v136);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v136);
    if ( (int)v117 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v117, v98, v99, v100);
    if ( v97 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v97, v98, v99, v100);
    v119 = 0;
    v118 = 0;
    v101 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v124[0] + 136LL))(
             v124[0],
             &v119);
    if ( v101 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v101, v102, v103, v104);
    v105 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v124[0] + 152LL))(
             v124[0],
             &v118);
    if ( v105 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v105, v106, v107, v108);
    v134[0] = v119;
    v134[1] = v118;
    *(_OWORD *)v121 = 0;
    LODWORD(v117) = 0;
    v109 = (__int64 **)xpsrdr::RenderState::GetRenderTargetStackTop(v62);
    v110 = *v109;
    v111 = **v109;
    *(_QWORD *)&v136[0] = 0;
    *((_QWORD *)&v136[0] + 1) = &v117;
    *(_QWORD *)&v136[1] = v121;
    v112 = (*(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base **, _OWORD *, std::_Ref_count_base *, _OWORD *))(v111 + 80))(
             v110,
             v134,
             v137,
             v126[0],
             v136);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v136);
    if ( (int)v117 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v117, v113, v114, v115);
    if ( v112 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v112, v113, v114, v115);
    *a1 = v121[0];
    a1[1] = v121[1];
    *(_OWORD *)v121 = 0;
    v95 = v124[1];
  }
  else
  {
    if ( *a4 != 9 )
      xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(*a4 - 8), v68, (int)v69);
    ++*(_DWORD *)(*((_QWORD *)v62 + 68) + 52LL);
    *(_OWORD *)v121 = 0;
    LODWORD(v117) = 0;
    v71 = *(__int64 (__fastcall ***)(std::_Ref_count_base *, GUID *, _OWORD *))v125[0];
    *(_QWORD *)&v136[0] = 0;
    *((_QWORD *)&v136[0] + 1) = &v117;
    *(_QWORD *)&v136[1] = v121;
    v72 = (*v71)(v125[0], &GUID_75f207e5_08bf_413c_96b1_b82b4064176b, v136);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v136);
    if ( (int)v117 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v117, v73, v74, v75);
    if ( v72 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v72, v73, v74, v75);
    v124[0] = 0;
    v118 = 0;
    v119 = 0;
    v76 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v121[0] + 136LL))(
            v121[0],
            v124);
    if ( v76 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v76, v77, v78, v79);
    v80 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v121[0] + 168LL))(
            v121[0],
            &v118);
    if ( v80 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v80, v81, v82, v83);
    v84 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v121[0] + 152LL))(
            v121[0],
            &v119);
    if ( v84 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v84, v85, v86, v87);
    v131 = v124[0];
    *(float *)&v132 = *(float *)&v118 - *(float *)v124;
    *((float *)&v132 + 1) = *((float *)&v118 + 1) - *((float *)v124 + 1);
    v133 = (std::_Ref_count_base **)v119;
    *(_OWORD *)v134 = 0;
    LODWORD(v117) = 0;
    v88 = (__int64 **)xpsrdr::RenderState::GetRenderTargetStackTop(v62);
    v89 = *v88;
    v90 = **v88;
    *(_QWORD *)&v136[0] = 0;
    *((_QWORD *)&v136[0] + 1) = &v117;
    *(_QWORD *)&v136[1] = v134;
    v91 = (*(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base **, _OWORD *, std::_Ref_count_base *, _OWORD *))(v90 + 88))(
            v89,
            &v131,
            v137,
            v126[0],
            v136);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v136);
    if ( (int)v117 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v117, v92, v93, v94);
    if ( v91 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v91, v92, v93, v94);
    *a1 = v134[0];
    a1[1] = v134[1];
    *(_OWORD *)v134 = 0;
    v95 = v121[1];
  }
  if ( v95 )
    std::_Ref_count_base::_Decref(v95);
  if ( v126[1] )
    std::_Ref_count_base::_Decref(v126[1]);
  std::vector<D2D1_GRADIENT_STOP>::_Tidy(&v128);
  if ( v127[1] )
    std::_Ref_count_base::_Decref(v127[1]);
  if ( v130[1] )
    std::_Ref_count_base::_Decref(v130[1]);
  if ( v125[1] )
    std::_Ref_count_base::_Decref(v125[1]);
  return a1;
}

```

## disassembly

```asm
0x1800b4a80  mov     rax, rsp
0x1800b4a83  mov     [rax+20h], rbx
0x1800b4a87  push    rbp
0x1800b4a88  push    rsi
0x1800b4a89  push    rdi
0x1800b4a8a  push    r12
0x1800b4a8c  push    r13
0x1800b4a8e  push    r14
0x1800b4a90  push    r15
0x1800b4a92  lea     rbp, [rsp-80h]
0x1800b4a97  sub     rsp, 180h
0x1800b4a9e  movaps  xmmword ptr [rax-48h], xmm6
0x1800b4aa2  mov     rax, cs:__security_cookie
0x1800b4aa9  xor     rax, rsp
0x1800b4aac  mov     [rbp+0B0h+var_48], rax
0x1800b4ab0  mov     r13, r9
0x1800b4ab3  mov     [rsp+1B0h+var_160], rdx
0x1800b4ab8  mov     rsi, rcx
0x1800b4abb  mov     [rsp+1B0h+var_168], rcx
0x1800b4ac0  mov     rdi, [rbp+0B0h+arg_20]
0x1800b4ac7  mov     [rsp+1B0h+var_168], rdi
0x1800b4acc  xor     r14d, r14d
0x1800b4acf  xorps   xmm0, xmm0
0x1800b4ad2  movdqu  xmmword ptr [rbp+0B0h+var_128], xmm0
0x1800b4ad7  mov     dword ptr [rsp+1B0h+var_170], r14d
0x1800b4adc  mov     rcx, [r8]
0x1800b4adf  mov     rax, [rcx]
0x1800b4ae2  mov     [rbp+0B0h+var_C8], r14
0x1800b4ae6  lea     rdx, [rsp+1B0h+var_170]
0x1800b4aeb  mov     [rbp+0B0h+var_C0], rdx
0x1800b4aef  lea     rdx, [rbp+0B0h+var_128]
0x1800b4af3  mov     [rbp+0B0h+var_B8], rdx
0x1800b4af7  lea     r8, [rbp+0B0h+var_C8]
0x1800b4afb  lea     rdx, _GUID_edb59622_61a2_42c3_bace_acf2286c06bf
0x1800b4b02  mov     rax, [rax]
0x1800b4b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b0a  mov     ebx, eax
0x1800b4b0c  lea     rcx, [rbp+0B0h+var_C8]
0x1800b4b10  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b4b15  mov     ecx, dword ptr [rsp+1B0h+var_170]; this
0x1800b4b19  test    ecx, ecx
0x1800b4b1b  jns     short loc_1800B4B23
0x1800b4b1d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4b23  test    ebx, ebx
0x1800b4b25  jns     short loc_1800B4B2F
0x1800b4b27  mov     ecx, ebx; this
0x1800b4b29  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4b2f  xorps   xmm0, xmm0
0x1800b4b32  movups  [rbp+0B0h+var_68], xmm0
0x1800b4b36  movups  [rbp+0B0h+var_68+0Ch], xmm0
0x1800b4b3a  mov     rcx, [rbp+0B0h+var_128]
0x1800b4b3e  mov     rax, [rcx]
0x1800b4b41  lea     rdx, [rbp+0B0h+var_68]
0x1800b4b45  mov     rax, [rax+28h]
0x1800b4b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b4e  test    eax, eax
0x1800b4b50  jns     short loc_1800B4B5A
0x1800b4b52  mov     ecx, eax; this
0x1800b4b54  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4b5a  xorps   xmm0, xmm0
0x1800b4b5d  movdqu  xmmword ptr [rbp+0B0h+var_E0], xmm0
0x1800b4b62  mov     dword ptr [rsp+1B0h+var_170], r14d
0x1800b4b67  mov     rcx, [rbp+0B0h+var_128]
0x1800b4b6b  mov     rax, [rcx]
0x1800b4b6e  mov     [rbp+0B0h+var_C8], r14
0x1800b4b72  lea     rdx, [rsp+1B0h+var_170]
0x1800b4b77  mov     [rbp+0B0h+var_C0], rdx
0x1800b4b7b  lea     rdx, [rbp+0B0h+var_E0]
0x1800b4b7f  mov     [rbp+0B0h+var_B8], rdx
0x1800b4b83  lea     rdx, [rbp+0B0h+var_C8]
0x1800b4b87  mov     rax, [rax+40h]
0x1800b4b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b90  mov     ebx, eax
0x1800b4b92  lea     rcx, [rbp+0B0h+var_C8]
0x1800b4b96  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b4b9b  mov     ecx, dword ptr [rsp+1B0h+var_170]; this
0x1800b4b9f  test    ecx, ecx
0x1800b4ba1  jns     short loc_1800B4BA9
0x1800b4ba3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4ba9  test    ebx, ebx
0x1800b4bab  jns     short loc_1800B4BB5
0x1800b4bad  mov     ecx, ebx; this
0x1800b4baf  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4bb5  xorps   xmm6, xmm6
0x1800b4bb8  mov     rcx, [rbp+0B0h+var_E0]
0x1800b4bbc  test    rcx, rcx
0x1800b4bbf  jz      short loc_1800B4C08
0x1800b4bc1  xorps   xmm0, xmm0
0x1800b4bc4  xor     eax, eax
0x1800b4bc6  movups  xmmword ptr [rbp+0B0h+var_B0], xmm0
0x1800b4bca  mov     [rbp+0B0h+var_A0], rax
0x1800b4bce  mov     rax, [rcx]
0x1800b4bd1  lea     rdx, [rbp+0B0h+var_B0]
0x1800b4bd5  mov     rax, [rax+28h]
0x1800b4bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4bde  test    eax, eax
0x1800b4be0  jns     short loc_1800B4BEA
0x1800b4be2  mov     ecx, eax; this
0x1800b4be4  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4bea  movups  xmm0, xmmword ptr [rbp+0B0h+var_B0]
0x1800b4bee  movups  [rbp+0B0h+var_68+4], xmm0
0x1800b4bf2  movss   xmm0, dword ptr [rbp+0B0h+var_A0]
0x1800b4bf7  movss   dword ptr [rbp+0B0h+var_54], xmm0
0x1800b4bfc  movss   xmm1, dword ptr [rbp+0B0h+var_A0+4]
0x1800b4c01  movss   dword ptr [rbp+0B0h+var_54+4], xmm1
0x1800b4c06  jmp     short loc_1800B4C1C
0x1800b4c08  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x1800b4c10  movups  [rbp+0B0h+var_68+4], xmm0
0x1800b4c14  mov     [rbp+0B0h+var_54], 0
0x1800b4c1c  mov     [rsp+1B0h+var_140], r14d
0x1800b4c21  mov     rcx, [rbp+0B0h+var_128]
0x1800b4c25  mov     rax, [rcx]
0x1800b4c28  lea     rdx, [rsp+1B0h+var_140]
0x1800b4c2d  mov     rax, [rax+68h]
0x1800b4c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4c36  test    eax, eax
0x1800b4c38  jns     short loc_1800B4C42
0x1800b4c3a  mov     ecx, eax; this
0x1800b4c3c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4c42  mov     ecx, [rsp+1B0h+var_140]
0x1800b4c46  sub     ecx, 1
0x1800b4c49  jz      short loc_1800B4C6B
0x1800b4c4b  sub     ecx, 1; this
0x1800b4c4e  jz      short loc_1800B4C63
0x1800b4c50  cmp     ecx, 1
0x1800b4c53  jz      short loc_1800B4C5B
0x1800b4c55  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800b4c5b  mov     r15d, 1
0x1800b4c61  jmp     short loc_1800B4C6E
0x1800b4c63  mov     r15d, 2
0x1800b4c69  jmp     short loc_1800B4C6E
0x1800b4c6b  mov     r15d, r14d
0x1800b4c6e  mov     [rsp+1B0h+var_13C], r14d
0x1800b4c73  mov     rcx, [rbp+0B0h+var_128]
0x1800b4c77  mov     rax, [rcx]
0x1800b4c7a  lea     rdx, [rsp+1B0h+var_13C]
0x1800b4c7f  mov     rax, [rax+78h]
0x1800b4c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4c88  test    eax, eax
0x1800b4c8a  jns     short loc_1800B4C94
0x1800b4c8c  mov     ecx, eax; this
0x1800b4c8e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4c94  mov     ecx, [rsp+1B0h+var_13C]
0x1800b4c98  sub     ecx, 1; this
0x1800b4c9b  jz      short loc_1800B4CAD
0x1800b4c9d  cmp     ecx, 1
0x1800b4ca0  jz      short loc_1800B4CA8
0x1800b4ca2  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800b4ca8  mov     r12d, r14d
0x1800b4cab  jmp     short loc_1800B4CB3
0x1800b4cad  mov     r12d, 1
0x1800b4cb3  xorps   xmm0, xmm0
0x1800b4cb6  movdqu  xmmword ptr [rbp+0B0h+var_108], xmm0
0x1800b4cbb  mov     dword ptr [rsp+1B0h+var_170], r14d
0x1800b4cc0  mov     rcx, [rbp+0B0h+var_128]
0x1800b4cc4  mov     rax, [rcx]
0x1800b4cc7  mov     [rbp+0B0h+var_C8], r14
0x1800b4ccb  lea     rdx, [rsp+1B0h+var_170]
0x1800b4cd0  mov     [rbp+0B0h+var_C0], rdx
0x1800b4cd4  lea     rdx, [rbp+0B0h+var_108]
0x1800b4cd8  mov     [rbp+0B0h+var_B8], rdx
0x1800b4cdc  lea     rdx, [rbp+0B0h+var_C8]
0x1800b4ce0  mov     rax, [rax+38h]
0x1800b4ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4ce9  mov     ebx, eax
0x1800b4ceb  lea     rcx, [rbp+0B0h+var_C8]
0x1800b4cef  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b4cf4  mov     ecx, dword ptr [rsp+1B0h+var_170]; this
0x1800b4cf8  test    ecx, ecx
0x1800b4cfa  jns     short loc_1800B4D02
0x1800b4cfc  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4d02  test    ebx, ebx
0x1800b4d04  jns     short loc_1800B4D0E
0x1800b4d06  mov     ecx, ebx; this
0x1800b4d08  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4d0e  mov     [rsp+1B0h+var_158], r14d
0x1800b4d13  mov     rcx, [rbp+0B0h+var_108]
0x1800b4d17  mov     rax, [rcx]
0x1800b4d1a  lea     rdx, [rsp+1B0h+var_158]
0x1800b4d1f  mov     rax, [rax+18h]
0x1800b4d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d28  test    eax, eax
0x1800b4d2a  jns     short loc_1800B4D34
0x1800b4d2c  mov     ecx, eax; this
0x1800b4d2e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4d34  xorps   xmm0, xmm0
0x1800b4d37  movdqu  [rbp+0B0h+var_F8], xmm0
0x1800b4d3c  mov     [rbp+0B0h+var_E8], r14
0x1800b4d40  mov     edx, [rsp+1B0h+var_158]
0x1800b4d44  lea     rcx, [rbp+0B0h+var_F8]
0x1800b4d48  call    ??$_Construct_n@$$V@?$vector@UD2D1_GRADIENT_STOP@@V?$allocator@UD2D1_GRADIENT_STOP@@@std@@@std@@AEAAX_K@Z; std::vector<D2D1_GRADIENT_STOP>::_Construct_n<>(unsigned __int64)
0x1800b4d4d  nop
0x1800b4d4e  mov     rbx, r14
0x1800b4d51  mov     r10d, [rsp+1B0h+var_158]
0x1800b4d56  cmp     rbx, r10
0x1800b4d59  jnb     loc_1800B4ECC
0x1800b4d5f  xorps   xmm0, xmm0
0x1800b4d62  movdqu  xmmword ptr [rsp+1B0h+var_150], xmm0
0x1800b4d68  mov     dword ptr [rsp+1B0h+var_170], r14d
0x1800b4d6d  mov     rcx, [rbp+0B0h+var_108]
0x1800b4d71  mov     rax, [rcx]
0x1800b4d74  mov     [rbp+0B0h+var_C8], r14
0x1800b4d78  lea     rdx, [rsp+1B0h+var_170]
0x1800b4d7d  mov     [rbp+0B0h+var_C0], rdx
0x1800b4d81  lea     rdx, [rsp+1B0h+var_150]
0x1800b4d86  mov     [rbp+0B0h+var_B8], rdx
0x1800b4d8a  mov     edx, ebx
0x1800b4d8c  lea     r8, [rbp+0B0h+var_C8]
0x1800b4d90  mov     rax, [rax+20h]
0x1800b4d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d99  mov     edi, eax
0x1800b4d9b  lea     rcx, [rbp+0B0h+var_C8]
0x1800b4d9f  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b4da4  mov     ecx, dword ptr [rsp+1B0h+var_170]; this
0x1800b4da8  test    ecx, ecx
0x1800b4daa  js      loc_1800B4EC6
0x1800b4db0  test    edi, edi
0x1800b4db2  js      loc_1800B4EBE
0x1800b4db8  mov     r8, [rsp+1B0h+var_150]
0x1800b4dbd  lea     r14, [rbx+rbx*4]
0x1800b4dc1  mov     rcx, [r8]
0x1800b4dc4  mov     rax, qword ptr [rbp+0B0h+var_F8]
0x1800b4dc8  lea     rdx, [rax+r14*4]
0x1800b4dcc  mov     rax, [rcx+20h]
0x1800b4dd0  mov     rcx, r8
0x1800b4dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4dd8  test    eax, eax
0x1800b4dda  js      loc_1800B4EB6
0x1800b4de0  xorps   xmm0, xmm0
0x1800b4de3  movups  [rbp+0B0h+var_98], xmm0
0x1800b4de7  movups  xmmword ptr [rbp+0B0h+var_88], xmm0
0x1800b4deb  movups  xmmword ptr [rbp+0B0h+var_88+0Ch], xmm0
0x1800b4def  movdqu  xmmword ptr [rbp+0B0h+var_B0], xmm0
0x1800b4df4  mov     dword ptr [rsp+1B0h+var_170], 0
0x1800b4dfc  mov     rcx, [rsp+1B0h+var_150]
0x1800b4e01  mov     rax, [rcx]
0x1800b4e04  mov     [rbp+0B0h+var_C8], 0
0x1800b4e0c  lea     rdx, [rsp+1B0h+var_170]
0x1800b4e11  mov     [rbp+0B0h+var_C0], rdx
0x1800b4e15  lea     rdx, [rbp+0B0h+var_B0]
0x1800b4e19  mov     [rbp+0B0h+var_B8], rdx
0x1800b4e1d  lea     r8, [rbp+0B0h+var_C8]
0x1800b4e21  lea     rdx, [rbp+0B0h+var_98]
0x1800b4e25  mov     rax, [rax+30h]
0x1800b4e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4e2e  mov     edi, eax
0x1800b4e30  lea     rcx, [rbp+0B0h+var_C8]
0x1800b4e34  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b4e39  mov     ecx, dword ptr [rsp+1B0h+var_170]; this
0x1800b4e3d  test    ecx, ecx
0x1800b4e3f  js      short loc_1800B4EB0
0x1800b4e41  test    edi, edi
0x1800b4e43  js      short loc_1800B4EA8
0x1800b4e45  lea     r9, [rbp+0B0h+var_B0]
0x1800b4e49  lea     r8, [rbp+0B0h+var_98]
0x1800b4e4d  mov     rdx, [rsp+1B0h+var_160]
0x1800b4e52  lea     rcx, [rsp+1B0h+var_138]
0x1800b4e57  call    ?GetD2D1Color@xpsrdr@@YA?AU_D3DCOLORVALUE@@AEAURenderState@1@AEBU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@std@@@Z; xpsrdr::GetD2D1Color(xpsrdr::RenderState &,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024 const &,std::shared_ptr<IXpsOMColorProfileResource> const &)
0x1800b4e5c  movdqu  xmm0, xmmword ptr [rax]
0x1800b4e60  mov     rax, qword ptr [rbp+0B0h+var_F8]
0x1800b4e64  movdqu  xmmword ptr [rax+r14*4+4], xmm0
0x1800b4e6b  movss   xmm1, dword ptr [rbp+0B0h+var_68]
0x1800b4e70  mov     rax, qword ptr [rbp+0B0h+var_F8]
0x1800b4e74  mulss   xmm1, dword ptr [rax+r14*4+10h]
0x1800b4e7b  addss   xmm6, xmm1
0x1800b4e7f  mov     rcx, [rbp+0B0h+var_B0+8]; this
0x1800b4e83  xor     r14d, r14d
0x1800b4e86  test    rcx, rcx
0x1800b4e89  jz      short loc_1800B4E91
0x1800b4e8b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b4e90  nop
0x1800b4e91  mov     rcx, [rsp+1B0h+var_150+8]; this
0x1800b4e96  test    rcx, rcx
0x1800b4e99  jz      short loc_1800B4EA0
0x1800b4e9b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b4ea0  inc     rbx
0x1800b4ea3  jmp     loc_1800B4D51
0x1800b4ea8  mov     ecx, edi; this
0x1800b4eaa  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4eb0  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4eb6  mov     ecx, eax; this
0x1800b4eb8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4ebe  mov     ecx, edi; this
0x1800b4ec0  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4ec6  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4ecc  mov     rdi, [rsp+1B0h+var_168]
0x1800b4ed1  test    rdi, rdi
0x1800b4ed4  jz      short loc_1800B4EEB
0x1800b4ed6  test    r10d, r10d
0x1800b4ed9  jz      short loc_1800B4EEB
0x1800b4edb  xorps   xmm0, xmm0
0x1800b4ede  cvtsi2ss xmm0, r10
0x1800b4ee3  divss   xmm6, xmm0
0x1800b4ee7  movss   dword ptr [rdi], xmm6
0x1800b4eeb  xorps   xmm0, xmm0
0x1800b4eee  movdqu  xmmword ptr [rbp+0B0h+var_118], xmm0
0x1800b4ef3  mov     dword ptr [rsp+1B0h+var_170], r14d
0x1800b4ef8  mov     r14, [rsp+1B0h+var_160]
0x1800b4efd  mov     rcx, r14
0x1800b4f00  call    ?GetRenderTargetStackTop@RenderState@xpsrdr@@QEBAAEBV?$shared_ptr@UID2D1RenderTarget@@@std@@XZ; xpsrdr::RenderState::GetRenderTargetStackTop(void)
  ... truncated ...
```
