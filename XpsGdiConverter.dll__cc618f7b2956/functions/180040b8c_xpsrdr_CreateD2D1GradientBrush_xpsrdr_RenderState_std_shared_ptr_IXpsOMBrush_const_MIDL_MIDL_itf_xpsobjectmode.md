# xpsrdr::CreateD2D1GradientBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0014 const &,float *)

- ea: `0x180040b8c`
- end: `0x180041540`
- name: `?CreateD2D1GradientBrush@xpsrdr@@YA?AV?$shared_ptr@UID2D1Brush@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMBrush@@@3@AEBW4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0014@@PEAM@Z`
- size: `2484`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180040014`

## callees

- `0x180008830`
- `0x18000e4c4`
- `0x180011b2c`
- `0x180036250`
- `0x180037278`
- `0x1800372e4`
- `0x18003fcfc`
- `0x180040b8c`
- `0x1800418e0`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
std::_Ref_count_base **__fastcall xpsrdr::CreateD2D1GradientBrush(
        std::_Ref_count_base **a1,
        _QWORD *a2,
        _QWORD **a3,
        std::_Ref_count_base *a4,
        float *a5)
{
  std::_Ref_count_base *v5; // r14
  float *v8; // rsi
  unsigned int v9; // r12d
  __int64 (__fastcall ***v10)(_QWORD, GUID *, std::_Ref_count_base **); // rcx
  __int64 (__fastcall **v11)(_QWORD, GUID *, std::_Ref_count_base **); // rax
  int v12; // ebx
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  int v16; // eax
  int v17; // edx
  const char *v18; // r8
  int v19; // r9d
  __int64 v20; // rax
  int v21; // ebx
  int v22; // edx
  const char *v23; // r8
  int v24; // r9d
  float v25; // xmm6_4
  int v26; // eax
  int v27; // edx
  const char *v28; // r8
  int v29; // r9d
  int v30; // eax
  const char *v31; // rdx
  const char *v32; // r8
  int v33; // r9d
  int v34; // r15d
  int v35; // eax
  const char *v36; // rdx
  const char *v37; // r8
  int v38; // r9d
  __int64 v39; // rax
  int v40; // ebx
  int v41; // edx
  const char *v42; // r8
  int v43; // r9d
  int v44; // eax
  int v45; // edx
  const char *v46; // r8
  int v47; // r9d
  unsigned __int64 v48; // rbx
  __int64 v49; // r8
  __int64 v50; // rax
  int v51; // esi
  int v52; // edx
  const char *v53; // r8
  int v54; // r9d
  int v55; // eax
  int v56; // edx
  const char *v57; // r8
  int v58; // r9d
  __int64 v59; // rax
  int v60; // esi
  int v61; // edx
  const char *v62; // r8
  int v63; // r9d
  const __m128i *D2D1Color; // rax
  __int64 *v65; // rcx
  __int64 v66; // rax
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
  __int64 *v88; // rcx
  __int64 v89; // rax
  int v90; // ebx
  int v91; // edx
  const char *v92; // r8
  int v93; // r9d
  std::_Ref_count_base *v94; // rcx
  __int64 (__fastcall **v95)(std::_Ref_count_base *, GUID *, _OWORD *); // rax
  int v96; // ebx
  int v97; // edx
  const char *v98; // r8
  int v99; // r9d
  int v100; // eax
  int v101; // edx
  const char *v102; // r8
  int v103; // r9d
  int v104; // eax
  int v105; // edx
  const char *v106; // r8
  int v107; // r9d
  __int64 *v108; // rcx
  __int64 v109; // rax
  int v110; // ebx
  int v111; // edx
  const char *v112; // r8
  int v113; // r9d
  xpsrdr *v115; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v116; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v117; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v118; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v119[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v120; // [rsp+70h] [rbp-90h] BYREF
  int v121; // [rsp+74h] [rbp-8Ch] BYREF
  std::_Ref_count_base *v122[2]; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v123[2]; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v124[2]; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v125[2]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v126[2]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v127[4]; // [rsp+C8h] [rbp-38h] BYREF
  std::_Ref_count_base *v128; // [rsp+E8h] [rbp-18h] BYREF
  xpsrdr **v129; // [rsp+F0h] [rbp-10h]
  std::_Ref_count_base **v130; // [rsp+F8h] [rbp-8h]
  std::_Ref_count_base *v131[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v132; // [rsp+110h] [rbp+10h]
  _OWORD v133[3]; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v134[2]; // [rsp+148h] [rbp+48h] BYREF

  v5 = a4;
  v117 = a4;
  v8 = a5;
  v116 = (std::_Ref_count_base *)a5;
  v9 = 0;
  *(_OWORD *)v123 = 0;
  LODWORD(v115) = 0;
  v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, std::_Ref_count_base **))*a3;
  v11 = (__int64 (__fastcall **)(_QWORD, GUID *, std::_Ref_count_base **))**a3;
  v128 = 0;
  v129 = &v115;
  v130 = v123;
  v12 = (*v11)(v10, &GUID_edb59622_61a2_42c3_bace_acf2286c06bf, &v128);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v128);
  if ( (int)v115 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v13, v14, v15);
  if ( v12 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v13, v14, v15);
  memset(v134, 0, 28);
  v16 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _OWORD *))(*(_QWORD *)v123[0] + 40LL))(v123[0], v134);
  if ( v16 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v16, v17, v18, v19);
  *(_OWORD *)v126 = 0;
  LODWORD(v115) = 0;
  v20 = *(_QWORD *)v123[0];
  v128 = 0;
  v129 = &v115;
  v130 = v126;
  v21 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v20 + 64))(v123[0], &v128);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v128);
  if ( (int)v115 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v22, v23, v24);
  if ( v21 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v21, v22, v23, v24);
  v25 = 0.0;
  if ( v126[0] )
  {
    *(_OWORD *)v131 = 0;
    v132 = 0;
    v26 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v126[0] + 40LL))(
            v126[0],
            v131);
    if ( v26 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, v27, v28, v29);
    *(_OWORD *)((char *)v134 + 4) = *(_OWORD *)v131;
    *(_QWORD *)((char *)&v134[1] + 4) = v132;
  }
  else
  {
    *(__m128i *)((char *)v134 + 4) = _mm_load_si128((const __m128i *)&_xmm);
    *(_QWORD *)((char *)&v134[1] + 4) = 0;
  }
  v120 = 0;
  v30 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *))(*(_QWORD *)v123[0] + 104LL))(v123[0], &v120);
  if ( v30 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v30, (int)v31, v32, v33);
  switch ( v120 )
  {
    case 1:
      v34 = 0;
      break;
    case 2:
      v34 = 2;
      break;
    case 3:
      v34 = 1;
      break;
    default:
      xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(v120 - 2), v31, (int)v32);
  }
  v121 = 0;
  v35 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *))(*(_QWORD *)v123[0] + 120LL))(v123[0], &v121);
  if ( v35 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v35, (int)v36, v37, v38);
  if ( v121 == 1 )
  {
    v9 = 1;
  }
  else if ( v121 != 2 )
  {
    xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(v121 - 1), v36, (int)v37);
  }
  *(_OWORD *)v125 = 0;
  LODWORD(v115) = 0;
  v39 = *(_QWORD *)v123[0];
  v128 = 0;
  v129 = &v115;
  v130 = v125;
  v40 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v39 + 56))(v123[0], &v128);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v128);
  if ( (int)v115 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v41, v42, v43);
  if ( v40 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v40, v41, v42, v43);
  v118 = 0;
  v44 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, unsigned int *))(*(_QWORD *)v125[0] + 24LL))(v125[0], &v118);
  if ( v44 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v44, v45, v46, v47);
  std::vector<D2D1_GRADIENT_STOP>::vector<D2D1_GRADIENT_STOP>(v127, v118);
  v48 = 0;
  v49 = v118;
  if ( v118 )
  {
    do
    {
      *(_OWORD *)v119 = 0;
      LODWORD(v115) = 0;
      v50 = *(_QWORD *)v125[0];
      v128 = 0;
      v129 = &v115;
      v130 = v119;
      v51 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, std::_Ref_count_base **))(v50 + 32))(
              v125[0],
              (unsigned int)v48,
              &v128);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v128);
      if ( (int)v115 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v52, v53, v54);
      if ( v51 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v51, v52, v53, v54);
      v55 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, unsigned __int64))(*(_QWORD *)v119[0] + 32LL))(
              v119[0],
              v127[0] + 20 * v48);
      if ( v55 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v55, v56, v57, v58);
      memset(v133, 0, 44);
      *(_OWORD *)v131 = 0;
      LODWORD(v115) = 0;
      v59 = *(_QWORD *)v119[0];
      v128 = 0;
      v129 = &v115;
      v130 = v131;
      v60 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _OWORD *, std::_Ref_count_base **))(v59 + 48))(
              v119[0],
              v133,
              &v128);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v128);
      if ( (int)v115 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v61, v62, v63);
      if ( v60 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v60, v61, v62, v63);
      D2D1Color = (const __m128i *)xpsrdr::GetD2D1Color(v122, a2, v133, v131);
      *(__m128i *)(v127[0] + 20 * v48 + 4) = _mm_loadu_si128(D2D1Color);
      v25 = v25 + (float)(*(float *)v134 * *(float *)(v127[0] + 20 * v48 + 16));
      if ( v131[1] )
        std::_Ref_count_base::_Decref(v131[1]);
      if ( v119[1] )
        std::_Ref_count_base::_Decref(v119[1]);
      ++v48;
      v49 = v118;
    }
    while ( v48 < v118 );
    v8 = (float *)v116;
    v5 = v117;
  }
  if ( v8 && (_DWORD)v49 )
    *v8 = v25 / (float)(int)v49;
  *(_OWORD *)v124 = 0;
  LODWORD(v115) = 0;
  v65 = **(__int64 ***)(a2[70] + 8 * ((a2[71] - 1LL) & (a2[72] - 1LL + a2[73])));
  v66 = *v65;
  v128 = 0;
  v129 = &v115;
  v130 = v124;
  v67 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD, int, std::_Ref_count_base **))(v66 + 72))(
          v65,
          v127[0],
          v49,
          v9,
          v34,
          &v128);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v128);
  if ( (int)v115 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, (int)v68, v69, v70);
  if ( v67 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v67, (int)v68, v69, v70);
  if ( *(_DWORD *)v5 == 8 )
  {
    ++*(_DWORD *)(a2[68] + 48LL);
    *(_OWORD *)v122 = 0;
    LODWORD(v115) = 0;
    v95 = *(__int64 (__fastcall ***)(std::_Ref_count_base *, GUID *, _OWORD *))v123[0];
    *(_QWORD *)&v133[0] = 0;
    *((_QWORD *)&v133[0] + 1) = &v115;
    *(_QWORD *)&v133[1] = v122;
    v96 = (*v95)(v123[0], &GUID_005e279f_c30d_40ff_93ec_1950d3c528db, v133);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v133);
    if ( (int)v115 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v97, v98, v99);
    if ( v96 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v96, v97, v98, v99);
    v116 = 0;
    v117 = 0;
    v100 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v122[0] + 136LL))(
             v122[0],
             &v116);
    if ( v100 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v100, v101, v102, v103);
    v104 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v122[0] + 152LL))(
             v122[0],
             &v117);
    if ( v104 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v104, v105, v106, v107);
    v131[0] = v116;
    v131[1] = v117;
    *(_OWORD *)v119 = 0;
    LODWORD(v115) = 0;
    v108 = **(__int64 ***)(a2[70] + 8 * ((a2[71] - 1LL) & (a2[72] - 1LL + a2[73])));
    v109 = *v108;
    *(_QWORD *)&v133[0] = 0;
    *((_QWORD *)&v133[0] + 1) = &v115;
    *(_QWORD *)&v133[1] = v119;
    v110 = (*(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base **, _OWORD *, std::_Ref_count_base *, _OWORD *))(v109 + 80))(
             v108,
             v131,
             v134,
             v124[0],
             v133);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v133);
    if ( (int)v115 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v111, v112, v113);
    if ( v110 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v110, v111, v112, v113);
    *a1 = v119[0];
    a1[1] = v119[1];
    *(_OWORD *)v119 = 0;
    v94 = v122[1];
  }
  else
  {
    if ( *(_DWORD *)v5 != 9 )
      xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(*(_DWORD *)v5 - 8), v68, (int)v69);
    ++*(_DWORD *)(a2[68] + 52LL);
    *(_OWORD *)v119 = 0;
    LODWORD(v115) = 0;
    v71 = *(__int64 (__fastcall ***)(std::_Ref_count_base *, GUID *, _OWORD *))v123[0];
    *(_QWORD *)&v133[0] = 0;
    *((_QWORD *)&v133[0] + 1) = &v115;
    *(_QWORD *)&v133[1] = v119;
    v72 = (*v71)(v123[0], &GUID_75f207e5_08bf_413c_96b1_b82b4064176b, v133);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v133);
    if ( (int)v115 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v73, v74, v75);
    if ( v72 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v72, v73, v74, v75);
    v122[0] = 0;
    v117 = 0;
    v116 = 0;
    v76 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v119[0] + 136LL))(
            v119[0],
            v122);
    if ( v76 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v76, v77, v78, v79);
    v80 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v119[0] + 168LL))(
            v119[0],
            &v117);
    if ( v80 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v80, v81, v82, v83);
    v84 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v119[0] + 152LL))(
            v119[0],
            &v116);
    if ( v84 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v84, v85, v86, v87);
    v128 = v122[0];
    *(float *)&v129 = *(float *)&v117 - *(float *)v122;
    *((float *)&v129 + 1) = *((float *)&v117 + 1) - *((float *)v122 + 1);
    v130 = (std::_Ref_count_base **)v116;
    *(_OWORD *)v131 = 0;
    LODWORD(v115) = 0;
    v88 = **(__int64 ***)(a2[70] + 8 * ((a2[71] - 1LL) & (a2[72] - 1LL + a2[73])));
    v89 = *v88;
    *(_QWORD *)&v133[0] = 0;
    *((_QWORD *)&v133[0] + 1) = &v115;
    *(_QWORD *)&v133[1] = v131;
    v90 = (*(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base **, _OWORD *, std::_Ref_count_base *, _OWORD *))(v89 + 88))(
            v88,
            &v128,
            v134,
            v124[0],
            v133);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v133);
    if ( (int)v115 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v91, v92, v93);
    if ( v90 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v90, v91, v92, v93);
    *a1 = v131[0];
    a1[1] = v131[1];
    *(_OWORD *)v131 = 0;
    v94 = v119[1];
  }
  if ( v94 )
    std::_Ref_count_base::_Decref(v94);
  if ( v124[1] )
    std::_Ref_count_base::_Decref(v124[1]);
  std::vector<D2D1_GRADIENT_STOP>::_Tidy(v127);
  if ( v125[1] )
    std::_Ref_count_base::_Decref(v125[1]);
  if ( v126[1] )
    std::_Ref_count_base::_Decref(v126[1]);
  if ( v123[1] )
    std::_Ref_count_base::_Decref(v123[1]);
  return a1;
}

```

## disassembly

```asm
0x180040b8c  mov     rax, rsp
0x180040b8f  mov     [rax+20h], rbx
0x180040b93  push    rbp
0x180040b94  push    rsi
0x180040b95  push    rdi
0x180040b96  push    r12
0x180040b98  push    r13
0x180040b9a  push    r14
0x180040b9c  push    r15
0x180040b9e  lea     rbp, [rsp-80h]
0x180040ba3  sub     rsp, 180h
0x180040baa  movaps  xmmword ptr [rax-48h], xmm6
0x180040bae  mov     rax, cs:__security_cookie
0x180040bb5  xor     rax, rsp
0x180040bb8  mov     [rbp+0B0h+var_48], rax
0x180040bbc  mov     r14, r9
0x180040bbf  mov     [rsp+1B0h+var_160], r9
0x180040bc4  mov     r13, rdx
0x180040bc7  mov     rdi, rcx
0x180040bca  mov     [rsp+1B0h+var_168], rcx
0x180040bcf  mov     rsi, [rbp+0B0h+arg_20]
0x180040bd6  mov     [rsp+1B0h+var_168], rsi
0x180040bdb  xor     r12d, r12d
0x180040bde  xorps   xmm0, xmm0
0x180040be1  movdqu  xmmword ptr [rbp+0B0h+var_128], xmm0
0x180040be6  mov     dword ptr [rsp+1B0h+var_170], r12d
0x180040beb  mov     rcx, [r8]
0x180040bee  mov     rax, [rcx]
0x180040bf1  mov     [rbp+0B0h+var_C8], r12
0x180040bf5  lea     rdx, [rsp+1B0h+var_170]
0x180040bfa  mov     [rbp+0B0h+var_C0], rdx
0x180040bfe  lea     rdx, [rbp+0B0h+var_128]
0x180040c02  mov     [rbp+0B0h+var_B8], rdx
0x180040c06  lea     r8, [rbp+0B0h+var_C8]
0x180040c0a  lea     rdx, _GUID_edb59622_61a2_42c3_bace_acf2286c06bf
0x180040c11  mov     rax, [rax]
0x180040c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c19  mov     ebx, eax
0x180040c1b  lea     rcx, [rbp+0B0h+var_C8]
0x180040c1f  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180040c24  mov     ecx, dword ptr [rsp+1B0h+var_170]; this
0x180040c28  test    ecx, ecx
0x180040c2a  js      loc_180041458
0x180040c30  test    ebx, ebx
0x180040c32  js      loc_18004145E
0x180040c38  xorps   xmm0, xmm0
0x180040c3b  movups  [rbp+0B0h+var_68], xmm0
0x180040c3f  movups  [rbp+0B0h+var_68+0Ch], xmm0
0x180040c43  mov     rcx, [rbp+0B0h+var_128]
0x180040c47  mov     rax, [rcx]
0x180040c4a  lea     rdx, [rbp+0B0h+var_68]
0x180040c4e  mov     rax, [rax+28h]
0x180040c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c57  test    eax, eax
0x180040c59  js      loc_180041466
0x180040c5f  xorps   xmm0, xmm0
0x180040c62  movdqu  xmmword ptr [rbp+0B0h+var_F8], xmm0
0x180040c67  mov     dword ptr [rsp+1B0h+var_170], r12d
0x180040c6c  mov     rcx, [rbp+0B0h+var_128]
0x180040c70  mov     rax, [rcx]
0x180040c73  mov     [rbp+0B0h+var_C8], r12
0x180040c77  lea     rdx, [rsp+1B0h+var_170]
0x180040c7c  mov     [rbp+0B0h+var_C0], rdx
0x180040c80  lea     rdx, [rbp+0B0h+var_F8]
0x180040c84  mov     [rbp+0B0h+var_B8], rdx
0x180040c88  lea     rdx, [rbp+0B0h+var_C8]
0x180040c8c  mov     rax, [rax+40h]
0x180040c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c95  mov     ebx, eax
0x180040c97  lea     rcx, [rbp+0B0h+var_C8]
0x180040c9b  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180040ca0  mov     ecx, dword ptr [rsp+1B0h+var_170]; this
0x180040ca4  test    ecx, ecx
0x180040ca6  js      loc_18004146E
0x180040cac  test    ebx, ebx
0x180040cae  js      loc_180041474
0x180040cb4  xorps   xmm6, xmm6
0x180040cb7  mov     rcx, [rbp+0B0h+var_F8]
0x180040cbb  test    rcx, rcx
0x180040cbe  jz      short loc_180040D03
0x180040cc0  xorps   xmm0, xmm0
0x180040cc3  xor     eax, eax
0x180040cc5  movups  xmmword ptr [rbp+0B0h+var_B0], xmm0
0x180040cc9  mov     [rbp+0B0h+var_A0], rax
0x180040ccd  mov     rax, [rcx]
0x180040cd0  lea     rdx, [rbp+0B0h+var_B0]
0x180040cd4  mov     rax, [rax+28h]
0x180040cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cdd  test    eax, eax
0x180040cdf  js      loc_18004147C
0x180040ce5  movups  xmm0, xmmword ptr [rbp+0B0h+var_B0]
0x180040ce9  movups  [rbp+0B0h+var_68+4], xmm0
0x180040ced  movss   xmm0, dword ptr [rbp+0B0h+var_A0]
0x180040cf2  movss   dword ptr [rbp+0B0h+var_54], xmm0
0x180040cf7  movss   xmm1, dword ptr [rbp+0B0h+var_A0+4]
0x180040cfc  movss   dword ptr [rbp+0B0h+var_54+4], xmm1
0x180040d01  jmp     short loc_180040D17
0x180040d03  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x180040d0b  movups  [rbp+0B0h+var_68+4], xmm0
0x180040d0f  mov     [rbp+0B0h+var_54], 0
0x180040d17  mov     [rsp+1B0h+var_140], r12d
0x180040d1c  mov     rcx, [rbp+0B0h+var_128]
0x180040d20  mov     rax, [rcx]
0x180040d23  lea     rdx, [rsp+1B0h+var_140]
0x180040d28  mov     rax, [rax+68h]
0x180040d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d31  test    eax, eax
0x180040d33  js      loc_180041484
0x180040d39  mov     ecx, [rsp+1B0h+var_140]
0x180040d3d  sub     ecx, 1
0x180040d40  jz      short loc_180040D5D
0x180040d42  sub     ecx, 1; this
0x180040d45  jz      short loc_180040D55
0x180040d47  cmp     ecx, 1
0x180040d4a  jnz     loc_18004148C
0x180040d50  mov     r15d, ecx
0x180040d53  jmp     short loc_180040D60
0x180040d55  mov     r15d, 2
0x180040d5b  jmp     short loc_180040D60
0x180040d5d  mov     r15d, r12d
0x180040d60  mov     [rsp+1B0h+var_13C], r12d
0x180040d65  mov     rcx, [rbp+0B0h+var_128]
0x180040d69  mov     rax, [rcx]
0x180040d6c  lea     rdx, [rsp+1B0h+var_13C]
0x180040d71  mov     rax, [rax+78h]
0x180040d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d7a  test    eax, eax
0x180040d7c  js      loc_180041492
0x180040d82  mov     ecx, [rsp+1B0h+var_13C]
0x180040d86  sub     ecx, 1; this
0x180040d89  jz      short loc_180040D96
0x180040d8b  cmp     ecx, 1
0x180040d8e  jnz     loc_180041452
0x180040d94  jmp     short loc_180040D9C
0x180040d96  mov     r12d, 1
0x180040d9c  xorps   xmm0, xmm0
0x180040d9f  movdqu  xmmword ptr [rbp+0B0h+var_108], xmm0
0x180040da4  mov     dword ptr [rsp+1B0h+var_170], 0
0x180040dac  mov     rcx, [rbp+0B0h+var_128]
0x180040db0  mov     rax, [rcx]
0x180040db3  mov     [rbp+0B0h+var_C8], 0
0x180040dbb  lea     rdx, [rsp+1B0h+var_170]
0x180040dc0  mov     [rbp+0B0h+var_C0], rdx
0x180040dc4  lea     rdx, [rbp+0B0h+var_108]
0x180040dc8  mov     [rbp+0B0h+var_B8], rdx
0x180040dcc  lea     rdx, [rbp+0B0h+var_C8]
0x180040dd0  mov     rax, [rax+38h]
0x180040dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040dd9  mov     ebx, eax
0x180040ddb  lea     rcx, [rbp+0B0h+var_C8]
0x180040ddf  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180040de4  mov     ecx, dword ptr [rsp+1B0h+var_170]; this
0x180040de8  test    ecx, ecx
0x180040dea  js      loc_18004149A
0x180040df0  test    ebx, ebx
0x180040df2  js      loc_1800414A0
0x180040df8  mov     [rsp+1B0h+var_158], 0
0x180040e00  mov     rcx, [rbp+0B0h+var_108]
0x180040e04  mov     rax, [rcx]
0x180040e07  lea     rdx, [rsp+1B0h+var_158]
0x180040e0c  mov     rax, [rax+18h]
0x180040e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e15  test    eax, eax
0x180040e17  js      loc_1800414A8
0x180040e1d  mov     edx, [rsp+1B0h+var_158]
0x180040e21  lea     rcx, [rbp+0B0h+var_E8]
0x180040e25  call    ??0?$vector@UD2D1_GRADIENT_STOP@@V?$allocator@UD2D1_GRADIENT_STOP@@@std@@@std@@QEAA@_KAEBV?$allocator@UD2D1_GRADIENT_STOP@@@1@@Z; std::vector<D2D1_GRADIENT_STOP>::vector<D2D1_GRADIENT_STOP>(unsigned __int64,std::allocator<D2D1_GRADIENT_STOP> const &)
0x180040e2a  nop
0x180040e2b  xor     ebx, ebx
0x180040e2d  mov     r8d, [rsp+1B0h+var_158]
0x180040e32  test    r8d, r8d
0x180040e35  jz      loc_180040F9E
0x180040e3b  xorps   xmm0, xmm0
0x180040e3e  movdqu  xmmword ptr [rsp+1B0h+var_150], xmm0
0x180040e44  mov     dword ptr [rsp+1B0h+var_170], 0
0x180040e4c  mov     rcx, [rbp+0B0h+var_108]
0x180040e50  mov     rax, [rcx]
0x180040e53  mov     [rbp+0B0h+var_C8], 0
0x180040e5b  lea     rdx, [rsp+1B0h+var_170]
0x180040e60  mov     [rbp+0B0h+var_C0], rdx
0x180040e64  lea     rdx, [rsp+1B0h+var_150]
0x180040e69  mov     [rbp+0B0h+var_B8], rdx
0x180040e6d  mov     edx, ebx
0x180040e6f  lea     r8, [rbp+0B0h+var_C8]
0x180040e73  mov     rax, [rax+20h]
0x180040e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e7c  mov     esi, eax
0x180040e7e  lea     rcx, [rbp+0B0h+var_C8]
0x180040e82  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180040e87  mov     ecx, dword ptr [rsp+1B0h+var_170]; this
0x180040e8b  test    ecx, ecx
0x180040e8d  js      loc_1800414D4
0x180040e93  test    esi, esi
0x180040e95  js      loc_1800414CC
0x180040e9b  mov     rcx, [rsp+1B0h+var_150]
0x180040ea0  lea     r14, [rbx+rbx*4]
0x180040ea4  mov     r8, [rcx]
0x180040ea7  mov     rax, [rbp+0B0h+var_E8]
0x180040eab  lea     rdx, [rax+r14*4]
0x180040eaf  mov     rax, [r8+20h]
0x180040eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040eb8  test    eax, eax
0x180040eba  js      loc_1800414C4
0x180040ec0  xorps   xmm0, xmm0
0x180040ec3  movups  [rbp+0B0h+var_98], xmm0
0x180040ec7  movups  xmmword ptr [rbp+0B0h+var_88], xmm0
0x180040ecb  movups  xmmword ptr [rbp+0B0h+var_88+0Ch], xmm0
0x180040ecf  movdqu  xmmword ptr [rbp+0B0h+var_B0], xmm0
0x180040ed4  mov     dword ptr [rsp+1B0h+var_170], 0
0x180040edc  mov     rcx, [rsp+1B0h+var_150]
0x180040ee1  mov     rax, [rcx]
0x180040ee4  mov     [rbp+0B0h+var_C8], 0
0x180040eec  lea     rdx, [rsp+1B0h+var_170]
0x180040ef1  mov     [rbp+0B0h+var_C0], rdx
0x180040ef5  lea     rdx, [rbp+0B0h+var_B0]
0x180040ef9  mov     [rbp+0B0h+var_B8], rdx
0x180040efd  lea     r8, [rbp+0B0h+var_C8]
0x180040f01  lea     rdx, [rbp+0B0h+var_98]
0x180040f05  mov     rax, [rax+30h]
0x180040f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f0e  mov     esi, eax
0x180040f10  lea     rcx, [rbp+0B0h+var_C8]
0x180040f14  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180040f19  mov     ecx, dword ptr [rsp+1B0h+var_170]; this
0x180040f1d  test    ecx, ecx
0x180040f1f  js      loc_1800414BE
0x180040f25  test    esi, esi
0x180040f27  js      loc_1800414B6
0x180040f2d  lea     r9, [rbp+0B0h+var_B0]
0x180040f31  lea     r8, [rbp+0B0h+var_98]
0x180040f35  mov     rdx, r13
0x180040f38  lea     rcx, [rsp+1B0h+var_138]
0x180040f3d  call    ?GetD2D1Color@xpsrdr@@YA?AU_D3DCOLORVALUE@@AEAURenderState@1@AEBU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@std@@@Z; xpsrdr::GetD2D1Color(xpsrdr::RenderState &,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024 const &,std::shared_ptr<IXpsOMColorProfileResource> const &)
0x180040f42  movdqu  xmm0, xmmword ptr [rax]
0x180040f46  mov     rax, [rbp+0B0h+var_E8]
0x180040f4a  movdqu  xmmword ptr [rax+r14*4+4], xmm0
0x180040f51  movss   xmm1, dword ptr [rbp+0B0h+var_68]
0x180040f56  mov     rax, [rbp+0B0h+var_E8]
0x180040f5a  mulss   xmm1, dword ptr [rax+r14*4+10h]
0x180040f61  addss   xmm6, xmm1
0x180040f65  mov     rcx, [rbp+0B0h+var_B0+8]; this
0x180040f69  test    rcx, rcx
0x180040f6c  jz      short loc_180040F74
0x180040f6e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180040f73  nop
0x180040f74  mov     rcx, [rsp+1B0h+var_150+8]; this
0x180040f79  test    rcx, rcx
0x180040f7c  jz      short loc_180040F83
0x180040f7e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180040f83  inc     rbx
0x180040f86  mov     r8d, [rsp+1B0h+var_158]
0x180040f8b  cmp     rbx, r8
0x180040f8e  jb      loc_180040E3B
0x180040f94  mov     rsi, [rsp+1B0h+var_168]
0x180040f99  mov     r14, [rsp+1B0h+var_160]
0x180040f9e  test    rsi, rsi
0x180040fa1  jz      short loc_180040FBB
0x180040fa3  test    r8d, r8d
0x180040fa6  jz      short loc_180040FBB
0x180040fa8  mov     eax, r8d
0x180040fab  xorps   xmm0, xmm0
0x180040fae  cvtsi2ss xmm0, rax
0x180040fb3  divss   xmm6, xmm0
0x180040fb7  movss   dword ptr [rsi], xmm6
0x180040fbb  xorps   xmm0, xmm0
0x180040fbe  movdqu  xmmword ptr [rbp+0B0h+var_118], xmm0
0x180040fc3  xor     esi, esi
0x180040fc5  mov     dword ptr [rsp+1B0h+var_170], esi
0x180040fc9  mov     rcx, [r13+248h]
0x180040fd0  mov     rax, [r13+240h]
0x180040fd7  dec     rax
0x180040fda  add     rcx, rax
0x180040fdd  mov     rax, [r13+238h]
0x180040fe4  dec     rax
0x180040fe7  and     rcx, rax
0x180040fea  mov     rax, [r13+230h]
0x180040ff1  mov     rcx, [rax+rcx*8]
0x180040ff5  mov     rcx, [rcx]
0x180040ff8  mov     rax, [rcx]
0x180040ffb  mov     [rbp+0B0h+var_C8], rsi
0x180040fff  lea     rdx, [rsp+1B0h+var_170]
0x180041004  mov     [rbp+0B0h+var_C0], rdx
0x180041008  lea     rdx, [rbp+0B0h+var_118]
0x18004100c  mov     [rbp+0B0h+var_B8], rdx
0x180041010  lea     rdx, [rbp+0B0h+var_C8]
0x180041014  mov     [rsp+1B0h+var_188], rdx
0x180041019  mov     dword ptr [rsp+1B0h+var_190], r15d
0x18004101e  mov     r9d, r12d
0x180041021  mov     rdx, [rbp+0B0h+var_E8]
0x180041025  mov     rax, [rax+48h]
0x180041029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004102e  mov     ebx, eax
0x180041030  lea     rcx, [rbp+0B0h+var_C8]
0x180041034  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180041039  mov     ecx, dword ptr [rsp+1B0h+var_170]; this
0x18004103d  test    ecx, ecx
0x18004103f  js      loc_1800414B0
0x180041045  test    ebx, ebx
0x180041047  js      loc_1800414DA
0x18004104d  mov     ecx, [r14]
  ... truncated ...
```
