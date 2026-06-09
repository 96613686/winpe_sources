# xpsrdr::CreateD2D1PathGeometry(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGeometry> const &)

- ea: `0x1800b5da8`
- end: `0x1800b66e0`
- name: `?CreateD2D1PathGeometry@xpsrdr@@YA?AV?$shared_ptr@UID2D1Geometry@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMGeometry@@@3@@Z`
- size: `2360`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800af8f4`
- `0x1800b0710`

## callees

- `0x180003180`
- `0x180003cc4`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a7db8`
- `0x1800a831c`
- `0x1800ad2c4`
- `0x1800b20e8`
- `0x1800b2154`
- `0x1800b5b64`
- `0x1800b5c70`
- `0x1800b5da8`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
std::_Ref_count_base **__fastcall xpsrdr::CreateD2D1PathGeometry(std::_Ref_count_base **a1, __int64 a2, __int64 **a3)
{
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // ebx
  int v8; // edx
  const char *v9; // r8
  int v10; // r9d
  __int64 v11; // rax
  int v12; // ebx
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  int v16; // eax
  int v17; // edx
  const char *v18; // r8
  int v19; // r9d
  __int64 *v20; // rcx
  __int64 v21; // rax
  int v22; // ebx
  int v23; // edx
  const char *v24; // r8
  int v25; // r9d
  int v26; // eax
  int v27; // edx
  const char *v28; // r8
  int v29; // r9d
  int v30; // r12d
  unsigned __int64 v31; // r15
  __int64 v32; // rax
  int v33; // ebx
  int v34; // edx
  const char *v35; // r8
  int v36; // r9d
  int v37; // eax
  int v38; // edx
  const char *v39; // r8
  int v40; // r9d
  int v41; // eax
  int v42; // edx
  const char *v43; // r8
  int v44; // r9d
  int v45; // eax
  int v46; // edx
  const char *v47; // r8
  int v48; // r9d
  char *v49; // rdi
  unsigned __int64 v50; // rcx
  char *v51; // rax
  size_t v52; // rbx
  char *v53; // rdi
  unsigned __int64 v54; // rcx
  char *v55; // rax
  size_t v56; // rbx
  int v57; // eax
  int v58; // edx
  const char *v59; // r8
  int v60; // r9d
  char *v61; // rdi
  unsigned __int64 v62; // rcx
  char *v63; // rax
  size_t v64; // rbx
  int v65; // eax
  const char *v66; // rdx
  xpsrdr *v67; // rcx
  const char *v68; // r8
  int v69; // r9d
  int v70; // eax
  const char *v71; // rdx
  xpsrdr *v72; // rcx
  const char *v73; // r8
  int v74; // r9d
  int v75; // eax
  const char *v76; // rdx
  xpsrdr *v77; // rcx
  const char *v78; // r8
  int v79; // r9d
  __int128 *v80; // rbx
  unsigned __int64 v81; // rdi
  unsigned __int64 v82; // rsi
  int v83; // ecx
  const char *v84; // rdx
  __int64 v85; // rax
  int v86; // edx
  int v87; // edx
  int v88; // eax
  int v89; // edx
  const char *v90; // r8
  int v91; // r9d
  int v92; // r8d
  int v93; // eax
  int v94; // edx
  const char *v95; // r8
  int v96; // r9d
  __int64 *v97; // rcx
  __int64 v98; // rax
  int v99; // ebx
  int v100; // edx
  const char *v101; // r8
  int v102; // r9d
  int v103; // eax
  int v104; // edx
  const char *v105; // r8
  int v106; // r9d
  __int64 *v107; // rcx
  __int64 v108; // rax
  int v109; // ebx
  int v110; // edx
  const char *v111; // r8
  int v112; // r9d
  int v114; // [rsp+30h] [rbp-D0h] BYREF
  int v115; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v116; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v117; // [rsp+3Ch] [rbp-C4h] BYREF
  std::_Ref_count_base *v118[2]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v119[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *v120[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v121; // [rsp+70h] [rbp-90h]
  int v122; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v123; // [rsp+7Ch] [rbp-84h] BYREF
  int v124; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v125; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v126; // [rsp+88h] [rbp-78h] BYREF
  void *v127[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v128; // [rsp+A0h] [rbp-60h]
  std::_Ref_count_base **v129; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v130[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 *v131; // [rsp+C0h] [rbp-40h] BYREF
  void *v132; // [rsp+C8h] [rbp-38h]
  __int64 v133; // [rsp+D0h] [rbp-30h]
  std::_Ref_count_base *v134[2]; // [rsp+D8h] [rbp-28h] BYREF
  std::_Ref_count_base *v135[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v136; // [rsp+100h] [rbp+0h]
  __int128 v137; // [rsp+108h] [rbp+8h] BYREF
  std::_Ref_count_base **v138; // [rsp+118h] [rbp+18h]
  __int128 v139; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v140[12]; // [rsp+130h] [rbp+30h]
  xpsrdr *v141[2]; // [rsp+140h] [rbp+40h] BYREF
  std::_Ref_count_base **v142; // [rsp+150h] [rbp+50h]

  v136 = a2;
  v129 = a1;
  *(_OWORD *)v130 = 0;
  v114 = 0;
  v5 = *(__int64 **)(a2 + 16);
  v6 = *v5;
  *(_QWORD *)&v137 = 0;
  *((_QWORD *)&v137 + 1) = &v114;
  v138 = v130;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v6 + 80))(v5, &v137);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v137);
  if ( v114 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v114, v8, v9, v10);
  if ( v7 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v7, v8, v9, v10);
  *(_OWORD *)v118 = 0;
  v114 = 0;
  v11 = *(_QWORD *)v130[0];
  *(_QWORD *)&v137 = 0;
  *((_QWORD *)&v137 + 1) = &v114;
  v138 = v118;
  v12 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int128 *))(v11 + 136))(v130[0], &v137);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v137);
  if ( v114 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v114, v13, v14, v15);
  if ( v12 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v13, v14, v15);
  v122 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a3 + 48))(*a3, &v122);
  if ( v16 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v16, v17, v18, v19);
  (*(void (__fastcall **)(std::_Ref_count_base *, bool))(*(_QWORD *)v118[0] + 24LL))(v118[0], v122 == 2);
  *(_OWORD *)v134 = 0;
  v114 = 0;
  v20 = *a3;
  v21 = **a3;
  *(_QWORD *)&v137 = 0;
  *((_QWORD *)&v137 + 1) = &v114;
  v138 = v134;
  v22 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v21 + 40))(v20, &v137);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v137);
  if ( v114 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v114, v23, v24, v25);
  if ( v22 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v23, v24, v25);
  (*(void (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v118[0] + 32LL))(v118[0], 0);
  std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(v120);
  std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(v127);
  std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(&v131);
  v123 = 0;
  v26 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, unsigned int *))(*(_QWORD *)v134[0] + 24LL))(v134[0], &v123);
  if ( v26 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, v27, v28, v29);
  v30 = 1;
  v31 = 0;
LABEL_18:
  if ( v31 < v123 )
  {
    *(_OWORD *)v119 = 0;
    LODWORD(v141[0]) = 0;
    v32 = *(_QWORD *)v134[0];
    *(_QWORD *)&v137 = 0;
    *((_QWORD *)&v137 + 1) = v141;
    v138 = v119;
    v33 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, __int128 *))(v32 + 32))(
            v134[0],
            (unsigned int)v31,
            &v137);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v137);
    if ( SLODWORD(v141[0]) < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v141[0]), v34, v35, v36);
    if ( v33 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v33, v34, v35, v36);
    v129 = 0;
    v37 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base ***))(*(_QWORD *)v119[0] + 64LL))(
            v119[0],
            &v129);
    if ( v37 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v37, v38, v39, v40);
    v124 = 0;
    v41 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *))(*(_QWORD *)v119[0] + 96LL))(v119[0], &v124);
    if ( v41 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v41, v42, v43, v44);
    (*(void (__fastcall **)(std::_Ref_count_base *, unsigned __int64, bool))(*(_QWORD *)v118[0] + 40LL))(
      v118[0],
      _mm_unpacklo_ps((__m128)(unsigned int)v129, (__m128)HIDWORD(v129)).m128_u64[0],
      v124 == 0);
    v116 = 0;
    v45 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, unsigned int *))(*(_QWORD *)v119[0] + 112LL))(
            v119[0],
            &v116);
    if ( v45 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v45, v46, v47, v48);
    v49 = (char *)v120[1];
    v50 = ((char *)v120[1] - (char *)v120[0]) >> 2;
    if ( v116 >= v50 )
    {
      if ( v116 <= v50 )
        goto LABEL_31;
      if ( v116 > (unsigned __int64)((signed __int64)(v121 - (unsigned __int64)v120[0]) >> 2) )
      {
        std::vector<enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011>::_Resize_reallocate<std::_Value_init_tag>(
          v120,
          v116);
        goto LABEL_31;
      }
      v52 = 4 * (v116 - v50);
      memset_0(v120[1], 0, v52);
      v51 = &v49[v52];
    }
    else
    {
      v51 = (char *)v120[0] + 4 * v116;
    }
    v120[1] = v51;
LABEL_31:
    v53 = (char *)v127[1];
    v54 = ((char *)v127[1] - (char *)v127[0]) >> 2;
    if ( v116 >= v54 )
    {
      if ( v116 <= v54 )
        goto LABEL_38;
      if ( v116 > (unsigned __int64)((signed __int64)(v128 - (unsigned __int64)v127[0]) >> 2) )
      {
        std::vector<enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011>::_Resize_reallocate<std::_Value_init_tag>(
          v127,
          v116);
        goto LABEL_38;
      }
      v56 = 4 * (v116 - v54);
      memset_0(v127[1], 0, v56);
      v55 = &v53[v56];
    }
    else
    {
      v55 = (char *)v127[0] + 4 * v116;
    }
    v127[1] = v55;
LABEL_38:
    v117 = 0;
    v57 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, unsigned int *))(*(_QWORD *)v119[0] + 120LL))(
            v119[0],
            &v117);
    if ( v57 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v57, v58, v59, v60);
    v61 = (char *)v132;
    v62 = ((_BYTE *)v132 - (_BYTE *)v131) >> 2;
    if ( v117 < v62 )
    {
      v63 = (char *)v131 + 4 * v117;
LABEL_45:
      v132 = v63;
      goto LABEL_46;
    }
    if ( v117 > v62 )
    {
      if ( v117 <= (unsigned __int64)((v133 - (__int64)v131) >> 2) )
      {
        v64 = 4 * (v117 - v62);
        memset_0(v132, 0, v64);
        v63 = &v61[v64];
        goto LABEL_45;
      }
      std::vector<float>::_Resize_reallocate<std::_Value_init_tag>(&v131, v117);
    }
LABEL_46:
    v125 = v116;
    v65 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, unsigned int *, void *))(*(_QWORD *)v119[0] + 40LL))(
            v119[0],
            &v125,
            v120[0]);
    if ( v65 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v65, (int)v66, v68, v69);
    if ( v125 != v116 )
      xpsrdr::ThrowLogicException(v67, v66, (int)v68);
    v126 = v116;
    v70 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, unsigned int *, void *))(*(_QWORD *)v119[0] + 48LL))(
            v119[0],
            &v126,
            v127[0]);
    if ( v70 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v70, (int)v71, v73, v74);
    if ( v126 != v116 )
      xpsrdr::ThrowLogicException(v72, v71, (int)v73);
    v115 = v117;
    v75 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *, __int128 *))(*(_QWORD *)v119[0] + 32LL))(
            v119[0],
            &v115,
            v131);
    if ( v75 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v75, (int)v76, v78, v79);
    if ( v115 != v117 )
      xpsrdr::ThrowLogicException(v77, v76, (int)v78);
    v80 = v131;
    v81 = 0;
    v82 = ((char *)v120[1] - (char *)v120[0]) >> 2;
    while ( 1 )
    {
      if ( v81 >= v82 )
      {
        v114 = 0;
        v88 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *))(*(_QWORD *)v119[0] + 80LL))(v119[0], &v114);
        if ( v88 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v88, v89, v90, v91);
        v92 = v114;
        if ( v114 && !v30 )
        {
          v30 = 1;
          (*(void (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v118[0] + 32LL))(v118[0], 0);
          v92 = v114;
        }
        (*(void (__fastcall **)(std::_Ref_count_base *, bool))(*(_QWORD *)v118[0] + 64LL))(v118[0], v92 != 0);
        if ( v119[1] )
          std::_Ref_count_base::_Decref(v119[1]);
        ++v31;
        goto LABEL_18;
      }
      v83 = *((_DWORD *)v127[0] + v81);
      if ( v30 != v83 )
      {
        v30 = *((_DWORD *)v127[0] + v81);
        (*(void (__fastcall **)(std::_Ref_count_base *, bool))(*(_QWORD *)v118[0] + 32LL))(v118[0], v83 == 0);
      }
      v84 = (const char *)*((unsigned int *)v120[0] + v81);
      if ( *((_DWORD *)v120[0] + v81) == 1
        || *((_DWORD *)v120[0] + v81) == 2
        || *((_DWORD *)v120[0] + v81) == 3
        || *((_DWORD *)v120[0] + v81) == 4 )
      {
        break;
      }
      switch ( *((_DWORD *)v120[0] + v81) )
      {
        case 5:
          v139 = *v80;
          *(_QWORD *)v140 = *((_QWORD *)v80 + 2);
          (*(void (__fastcall **)(std::_Ref_count_base *, __int128 *, __int64))(*(_QWORD *)v118[0] + 56LL))(
            v118[0],
            &v139,
            1);
          v85 = 24;
          break;
        case 6:
          v141[0] = *(xpsrdr **)v80;
          (*(void (__fastcall **)(std::_Ref_count_base *, xpsrdr **, __int64))(*(_QWORD *)v118[0] + 48LL))(
            v118[0],
            v141,
            1);
          v85 = 8;
          break;
        case 7:
          *(_OWORD *)v141 = *v80;
          (*(void (__fastcall **)(std::_Ref_count_base *, xpsrdr **))(*(_QWORD *)v118[0] + 96LL))(v118[0], v141);
          v85 = 16;
          break;
        default:
          xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(*((_DWORD *)v120[0] + v81) - 6), v84, (int)v78);
      }
LABEL_72:
      ++v81;
      v80 = (__int128 *)((char *)v80 + v85);
    }
    *(_QWORD *)&v140[4] = 0;
    v139 = *v80;
    *(_DWORD *)v140 = *((_DWORD *)v80 + 4);
    v86 = (_DWORD)v84 - 1;
    if ( v86 )
    {
      v87 = v86 - 1;
      if ( v87 )
      {
        *(_QWORD *)&v140[4] = v87 == 1;
LABEL_71:
        (*(void (__fastcall **)(std::_Ref_count_base *, __int128 *))(*(_QWORD *)v118[0] + 112LL))(v118[0], &v139);
        v85 = 20;
        goto LABEL_72;
      }
    }
    else
    {
      *(_DWORD *)&v140[4] = 1;
    }
    *(_DWORD *)&v140[8] = 1;
    goto LABEL_71;
  }
  v93 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v118[0] + 72LL))(v118[0]);
  if ( v93 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v93, v94, v95, v96);
  *(_OWORD *)v135 = 0;
  v115 = 0;
  v97 = *a3;
  v98 = **a3;
  *(_QWORD *)&v137 = 0;
  *((_QWORD *)&v137 + 1) = &v115;
  v138 = v135;
  v99 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v98 + 64))(v97, &v137);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v137);
  if ( v115 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v100, v101, v102);
  if ( v99 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v99, v100, v101, v102);
  if ( v135[0] )
  {
    *(_OWORD *)v141 = 0;
    v142 = 0;
    v103 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, xpsrdr **))(*(_QWORD *)v135[0] + 40LL))(v135[0], v141);
    if ( v103 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v103, v104, v105, v106);
    *(_OWORD *)v119 = 0;
    v115 = 0;
    v107 = *(__int64 **)(v136 + 16);
    v108 = *v107;
    *(_QWORD *)&v139 = 0;
    *((_QWORD *)&v139 + 1) = &v115;
    *(_QWORD *)v140 = v119;
    v137 = *(_OWORD *)v141;
    v138 = v142;
    v109 = (*(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base *, __int128 *, __int128 *))(v108 + 72))(
             v107,
             v130[0],
             &v137,
             &v139);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v139);
    if ( v115 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v110, v111, v112);
    if ( v109 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v109, v110, v111, v112);
    *a1 = v119[0];
    a1[1] = v119[1];
    *(_OWORD *)v119 = 0;
  }
  else
  {
    *a1 = v130[0];
    a1[1] = v130[1];
    *(_OWORD *)v130 = 0;
  }
  if ( v135[1] )
    std::_Ref_count_base::_Decref(v135[1]);
  std::vector<float>::_Tidy(&v131);
  if ( v127[0] )
  {
    std::_Deallocate<16>(v127[0], (v128 - (unsigned __int64)v127[0]) & 0xFFFFFFFFFFFFFFFCuLL);
    *(_OWORD *)v127 = 0;
    v128 = 0;
  }
  if ( v120[0] )
  {
    std::_Deallocate<16>(v120[0], (v121 - (unsigned __int64)v120[0]) & 0xFFFFFFFFFFFFFFFCuLL);
    *(_OWORD *)v120 = 0;
    v121 = 0;
  }
  if ( v134[1] )
    std::_Ref_count_base::_Decref(v134[1]);
  if ( v118[1] )
    std::_Ref_count_base::_Decref(v118[1]);
  if ( v130[1] )
    std::_Ref_count_base::_Decref(v130[1]);
  return a1;
}

```

## disassembly

```asm
0x1800b5da8  mov     [rsp-8+arg_18], rbx
0x1800b5dad  push    rbp
0x1800b5dae  push    rsi
0x1800b5daf  push    rdi
0x1800b5db0  push    r12
0x1800b5db2  push    r13
0x1800b5db4  push    r14
0x1800b5db6  push    r15
0x1800b5db8  lea     rbp, [rsp-60h]
0x1800b5dbd  sub     rsp, 160h
0x1800b5dc4  mov     rax, cs:__security_cookie
0x1800b5dcb  xor     rax, rsp
0x1800b5dce  mov     [rbp+90h+var_38], rax
0x1800b5dd2  mov     r13, r8
0x1800b5dd5  mov     [rbp+90h+var_90], rdx
0x1800b5dd9  mov     r14, rcx
0x1800b5ddc  mov     [rbp+90h+var_E8], rcx
0x1800b5de0  xor     esi, esi
0x1800b5de2  xorps   xmm0, xmm0
0x1800b5de5  movdqu  xmmword ptr [rbp+90h+var_E0], xmm0
0x1800b5dea  mov     dword ptr [rsp+190h+var_160], esi
0x1800b5dee  mov     rcx, [rdx+10h]
0x1800b5df2  mov     rax, [rcx]
0x1800b5df5  mov     qword ptr [rbp+90h+var_88], rsi
0x1800b5df9  lea     rdx, [rsp+190h+var_160]
0x1800b5dfe  mov     qword ptr [rbp+90h+var_88+8], rdx
0x1800b5e02  lea     rdx, [rbp+90h+var_E0]
0x1800b5e06  mov     [rbp+90h+var_78], rdx
0x1800b5e0a  lea     rdx, [rbp+90h+var_88]
0x1800b5e0e  mov     rax, [rax+50h]
0x1800b5e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5e17  mov     ebx, eax
0x1800b5e19  lea     rcx, [rbp+90h+var_88]
0x1800b5e1d  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b5e22  mov     ecx, dword ptr [rsp+190h+var_160]; this
0x1800b5e26  test    ecx, ecx
0x1800b5e28  jns     short loc_1800B5E30
0x1800b5e2a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b5e30  test    ebx, ebx
0x1800b5e32  jns     short loc_1800B5E3C
0x1800b5e34  mov     ecx, ebx; this
0x1800b5e36  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b5e3c  xorps   xmm0, xmm0
0x1800b5e3f  movdqu  xmmword ptr [rsp+190h+var_150], xmm0
0x1800b5e45  mov     dword ptr [rsp+190h+var_160], esi
0x1800b5e49  mov     rcx, [rbp+90h+var_E0]
0x1800b5e4d  mov     rax, [rcx]
0x1800b5e50  mov     qword ptr [rbp+90h+var_88], rsi
0x1800b5e54  lea     rdx, [rsp+190h+var_160]
0x1800b5e59  mov     qword ptr [rbp+90h+var_88+8], rdx
0x1800b5e5d  lea     rdx, [rsp+190h+var_150]
0x1800b5e62  mov     [rbp+90h+var_78], rdx
0x1800b5e66  lea     rdx, [rbp+90h+var_88]
0x1800b5e6a  mov     rax, [rax+88h]
0x1800b5e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5e76  mov     ebx, eax
0x1800b5e78  lea     rcx, [rbp+90h+var_88]
0x1800b5e7c  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b5e81  mov     ecx, dword ptr [rsp+190h+var_160]; this
0x1800b5e85  test    ecx, ecx
0x1800b5e87  jns     short loc_1800B5E8F
0x1800b5e89  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b5e8f  test    ebx, ebx
0x1800b5e91  jns     short loc_1800B5E9B
0x1800b5e93  mov     ecx, ebx; this
0x1800b5e95  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b5e9b  mov     [rsp+190h+var_118], esi
0x1800b5e9f  mov     rcx, [r13+0]
0x1800b5ea3  mov     rax, [rcx]
0x1800b5ea6  lea     rdx, [rsp+190h+var_118]
0x1800b5eab  mov     rax, [rax+30h]
0x1800b5eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5eb4  test    eax, eax
0x1800b5eb6  jns     short loc_1800B5EC0
0x1800b5eb8  mov     ecx, eax; this
0x1800b5eba  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b5ec0  mov     rcx, [rsp+190h+var_150]
0x1800b5ec5  mov     rax, [rcx]
0x1800b5ec8  mov     edx, esi
0x1800b5eca  cmp     [rsp+190h+var_118], 2
0x1800b5ecf  setz    dl
0x1800b5ed2  mov     rax, [rax+18h]
0x1800b5ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5edb  xorps   xmm0, xmm0
0x1800b5ede  movdqu  xmmword ptr [rbp+90h+var_B8], xmm0
0x1800b5ee3  mov     dword ptr [rsp+190h+var_160], esi
0x1800b5ee7  mov     rcx, [r13+0]
0x1800b5eeb  mov     rax, [rcx]
0x1800b5eee  mov     qword ptr [rbp+90h+var_88], rsi
0x1800b5ef2  lea     rdx, [rsp+190h+var_160]
0x1800b5ef7  mov     qword ptr [rbp+90h+var_88+8], rdx
0x1800b5efb  lea     rdx, [rbp+90h+var_B8]
0x1800b5eff  mov     [rbp+90h+var_78], rdx
0x1800b5f03  lea     rdx, [rbp+90h+var_88]
0x1800b5f07  mov     rax, [rax+28h]
0x1800b5f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5f10  mov     ebx, eax
0x1800b5f12  lea     rcx, [rbp+90h+var_88]
0x1800b5f16  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b5f1b  mov     ecx, dword ptr [rsp+190h+var_160]; this
0x1800b5f1f  test    ecx, ecx
0x1800b5f21  jns     short loc_1800B5F29
0x1800b5f23  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b5f29  test    ebx, ebx
0x1800b5f2b  jns     short loc_1800B5F35
0x1800b5f2d  mov     ecx, ebx; this
0x1800b5f2f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b5f35  mov     rcx, [rsp+190h+var_150]
0x1800b5f3a  mov     rax, [rcx]
0x1800b5f3d  xor     edx, edx
0x1800b5f3f  mov     rax, [rax+20h]
0x1800b5f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5f48  lea     rcx, [rsp+190h+var_130]
0x1800b5f4d  call    ??0?$vector@V?$shared_ptr@UIXpsOMVisual@@@std@@V?$allocator@V?$shared_ptr@UIXpsOMVisual@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(void)
0x1800b5f52  nop
0x1800b5f53  lea     rcx, [rbp+90h+var_100]
0x1800b5f57  call    ??0?$vector@V?$shared_ptr@UIXpsOMVisual@@@std@@V?$allocator@V?$shared_ptr@UIXpsOMVisual@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(void)
0x1800b5f5c  nop
0x1800b5f5d  lea     rcx, [rbp+90h+var_D0]
0x1800b5f61  call    ??0?$vector@V?$shared_ptr@UIXpsOMVisual@@@std@@V?$allocator@V?$shared_ptr@UIXpsOMVisual@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(void)
0x1800b5f66  nop
0x1800b5f67  mov     [rsp+190h+var_114], esi
0x1800b5f6b  mov     rcx, [rbp+90h+var_B8]
0x1800b5f6f  mov     rax, [rcx]
0x1800b5f72  lea     rdx, [rsp+190h+var_114]
0x1800b5f77  mov     rax, [rax+18h]
0x1800b5f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5f80  test    eax, eax
0x1800b5f82  jns     short loc_1800B5F8C
0x1800b5f84  mov     ecx, eax; this
0x1800b5f86  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b5f8c  mov     r12d, 1
0x1800b5f92  mov     r15, rsi
0x1800b5f95  mov     eax, [rsp+190h+var_114]
0x1800b5f99  cmp     r15, rax
0x1800b5f9c  jnb     loc_1800B64C1
0x1800b5fa2  xorps   xmm0, xmm0
0x1800b5fa5  movdqu  xmmword ptr [rsp+190h+var_140], xmm0
0x1800b5fab  mov     dword ptr [rbp+90h+var_50], esi
0x1800b5fae  mov     rcx, [rbp+90h+var_B8]
0x1800b5fb2  mov     rax, [rcx]
0x1800b5fb5  mov     qword ptr [rbp+90h+var_88], rsi
0x1800b5fb9  lea     rdx, [rbp+90h+var_50]
0x1800b5fbd  mov     qword ptr [rbp+90h+var_88+8], rdx
0x1800b5fc1  lea     rdx, [rsp+190h+var_140]
0x1800b5fc6  mov     [rbp+90h+var_78], rdx
0x1800b5fca  mov     edx, r15d
0x1800b5fcd  lea     r8, [rbp+90h+var_88]
0x1800b5fd1  mov     rax, [rax+20h]
0x1800b5fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5fda  mov     ebx, eax
0x1800b5fdc  lea     rcx, [rbp+90h+var_88]
0x1800b5fe0  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b5fe5  mov     ecx, dword ptr [rbp+90h+var_50]; this
0x1800b5fe8  test    ecx, ecx
0x1800b5fea  js      loc_1800B64BB
0x1800b5ff0  test    ebx, ebx
0x1800b5ff2  js      loc_1800B64B3
0x1800b5ff8  xor     eax, eax
0x1800b5ffa  mov     [rbp+90h+var_E8], rax
0x1800b5ffe  mov     rcx, [rsp+190h+var_140]
0x1800b6003  mov     rax, [rcx]
0x1800b6006  lea     rdx, [rbp+90h+var_E8]
0x1800b600a  mov     rax, [rax+40h]
0x1800b600e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6013  test    eax, eax
0x1800b6015  js      loc_1800B64AB
0x1800b601b  mov     [rbp+90h+var_110], esi
0x1800b601e  mov     rcx, [rsp+190h+var_140]
0x1800b6023  mov     rax, [rcx]
0x1800b6026  lea     rdx, [rbp+90h+var_110]
0x1800b602a  mov     rax, [rax+60h]
0x1800b602e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6033  test    eax, eax
0x1800b6035  js      loc_1800B64A3
0x1800b603b  movss   xmm1, dword ptr [rbp+90h+var_E8]
0x1800b6040  movss   xmm0, dword ptr [rbp+90h+var_E8+4]
0x1800b6045  mov     rcx, [rsp+190h+var_150]
0x1800b604a  mov     rax, [rcx]
0x1800b604d  mov     r8d, esi
0x1800b6050  cmp     [rbp+90h+var_110], esi
0x1800b6053  setz    r8b
0x1800b6057  unpcklps xmm1, xmm0
0x1800b605a  movq    rdx, xmm1
0x1800b605f  mov     rax, [rax+28h]
0x1800b6063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6068  mov     [rsp+190h+var_158], esi
0x1800b606c  mov     rcx, [rsp+190h+var_140]
0x1800b6071  mov     rax, [rcx]
0x1800b6074  lea     rdx, [rsp+190h+var_158]
0x1800b6079  mov     rax, [rax+70h]
0x1800b607d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6082  test    eax, eax
0x1800b6084  js      loc_1800B649B
0x1800b608a  mov     ebx, [rsp+190h+var_158]
0x1800b608e  mov     rdx, [rsp+190h+var_130]
0x1800b6093  mov     rdi, [rsp+190h+var_130+8]
0x1800b6098  mov     rcx, rdi
0x1800b609b  sub     rcx, rdx
0x1800b609e  sar     rcx, 2
0x1800b60a2  cmp     rbx, rcx
0x1800b60a5  jnb     short loc_1800B60AD
0x1800b60a7  lea     rax, [rdx+rbx*4]
0x1800b60ab  jmp     short loc_1800B60E7
0x1800b60ad  jbe     short loc_1800B60EC
0x1800b60af  mov     rax, [rsp+190h+var_120]
0x1800b60b4  sub     rax, rdx
0x1800b60b7  sar     rax, 2
0x1800b60bb  cmp     rbx, rax
0x1800b60be  jbe     short loc_1800B60CF
0x1800b60c0  mov     rdx, rbx
0x1800b60c3  lea     rcx, [rsp+190h+var_130]
0x1800b60c8  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011@@V?$allocator@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800b60cd  jmp     short loc_1800B60EC
0x1800b60cf  sub     rbx, rcx
0x1800b60d2  shl     rbx, 2
0x1800b60d6  mov     r8, rbx; Size
0x1800b60d9  xor     edx, edx; Val
0x1800b60db  mov     rcx, rdi; void *
0x1800b60de  call    memset_0
0x1800b60e3  lea     rax, [rbx+rdi]
0x1800b60e7  mov     [rsp+190h+var_130+8], rax
0x1800b60ec  mov     ebx, [rsp+190h+var_158]
0x1800b60f0  mov     rdx, [rbp+90h+var_100]
0x1800b60f4  mov     rdi, [rbp+90h+var_100+8]
0x1800b60f8  mov     rcx, rdi
0x1800b60fb  sub     rcx, rdx
0x1800b60fe  sar     rcx, 2
0x1800b6102  cmp     rbx, rcx
0x1800b6105  jnb     short loc_1800B610D
0x1800b6107  lea     rax, [rdx+rbx*4]
0x1800b610b  jmp     short loc_1800B6145
0x1800b610d  jbe     short loc_1800B6149
0x1800b610f  mov     rax, [rbp+90h+var_F0]
0x1800b6113  sub     rax, rdx
0x1800b6116  sar     rax, 2
0x1800b611a  cmp     rbx, rax
0x1800b611d  jbe     short loc_1800B612D
0x1800b611f  mov     rdx, rbx
0x1800b6122  lea     rcx, [rbp+90h+var_100]
0x1800b6126  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011@@V?$allocator@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800b612b  jmp     short loc_1800B6149
0x1800b612d  sub     rbx, rcx
0x1800b6130  shl     rbx, 2
0x1800b6134  mov     r8, rbx; Size
0x1800b6137  xor     edx, edx; Val
0x1800b6139  mov     rcx, rdi; void *
0x1800b613c  call    memset_0
0x1800b6141  lea     rax, [rbx+rdi]
0x1800b6145  mov     [rbp+90h+var_100+8], rax
0x1800b6149  mov     [rsp+190h+var_154], esi
0x1800b614d  mov     rcx, [rsp+190h+var_140]
0x1800b6152  mov     rax, [rcx]
0x1800b6155  lea     rdx, [rsp+190h+var_154]
0x1800b615a  mov     rax, [rax+78h]
0x1800b615e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6163  test    eax, eax
0x1800b6165  js      loc_1800B6493
0x1800b616b  mov     ebx, [rsp+190h+var_154]
0x1800b616f  mov     rdx, [rbp+90h+var_D0]
0x1800b6173  mov     rdi, [rbp+90h+var_C8]
0x1800b6177  mov     rcx, rdi
0x1800b617a  sub     rcx, rdx
0x1800b617d  sar     rcx, 2
0x1800b6181  cmp     rbx, rcx
0x1800b6184  jnb     short loc_1800B618C
0x1800b6186  lea     rax, [rdx+rbx*4]
0x1800b618a  jmp     short loc_1800B61C4
0x1800b618c  jbe     short loc_1800B61C8
0x1800b618e  mov     rax, [rbp+90h+var_C0]
0x1800b6192  sub     rax, rdx
0x1800b6195  sar     rax, 2
0x1800b6199  cmp     rbx, rax
0x1800b619c  jbe     short loc_1800B61AC
0x1800b619e  mov     rdx, rbx
0x1800b61a1  lea     rcx, [rbp+90h+var_D0]
0x1800b61a5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@MV?$allocator@M@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<float>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800b61aa  jmp     short loc_1800B61C8
0x1800b61ac  sub     rbx, rcx
0x1800b61af  shl     rbx, 2
0x1800b61b3  mov     r8, rbx; Size
0x1800b61b6  xor     edx, edx; Val
0x1800b61b8  mov     rcx, rdi; void *
0x1800b61bb  call    memset_0
0x1800b61c0  lea     rax, [rbx+rdi]
0x1800b61c4  mov     [rbp+90h+var_C8], rax
0x1800b61c8  mov     eax, [rsp+190h+var_158]
0x1800b61cc  mov     [rbp+90h+var_10C], eax
0x1800b61cf  mov     rcx, [rsp+190h+var_140]
0x1800b61d4  mov     rax, [rcx]
0x1800b61d7  mov     r8, [rsp+190h+var_130]
0x1800b61dc  lea     rdx, [rbp+90h+var_10C]
0x1800b61e0  mov     rax, [rax+28h]
0x1800b61e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b61e9  test    eax, eax
0x1800b61eb  js      loc_1800B648B
0x1800b61f1  mov     eax, [rsp+190h+var_158]
0x1800b61f5  cmp     [rbp+90h+var_10C], eax
0x1800b61f8  jnz     loc_1800B6485
0x1800b61fe  mov     [rbp+90h+var_108], eax
  ... truncated ...
```
