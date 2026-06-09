# xpsrdr::CreateD2D1PathGeometry(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGeometry> const &)

- ea: `0x18003b810`
- end: `0x18003c014`
- name: `?CreateD2D1PathGeometry@xpsrdr@@YA?AV?$shared_ptr@UID2D1Geometry@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMGeometry@@@3@@Z`
- size: `2052`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800109e0`
- `0x1800122fc`
- `0x1800393b4`
- `0x18003a18c`

## callees

- `0x180008830`
- `0x18000e130`
- `0x18000e15c`
- `0x18000e174`
- `0x18000e4c4`
- `0x18000e990`
- `0x180011b0c`
- `0x180011d1c`
- `0x18002ba80`
- `0x180037278`
- `0x1800372e4`
- `0x18003b810`
- `0x18003c01c`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall xpsrdr::CreateD2D1PathGeometry(__int64 a1, __int64 a2, __int64 **a3)
{
  __int64 v5; // rdx
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // ebx
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  __int64 v12; // rax
  int v13; // ebx
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  int v17; // eax
  int v18; // edx
  const char *v19; // r8
  int v20; // r9d
  __int64 *v21; // rcx
  __int64 v22; // rax
  int v23; // ebx
  int v24; // edx
  const char *v25; // r8
  int v26; // r9d
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  int v30; // eax
  int v31; // edx
  const char *v32; // r8
  int v33; // r9d
  int v34; // r14d
  unsigned __int64 v35; // r15
  __int64 v36; // rax
  int v37; // ebx
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
  int v49; // eax
  int v50; // edx
  const char *v51; // r8
  int v52; // r9d
  int v53; // eax
  int v54; // edx
  const char *v55; // r8
  int v56; // r9d
  int v57; // eax
  const char *v58; // rdx
  xpsrdr *v59; // rcx
  const char *v60; // r8
  int v61; // r9d
  int v62; // eax
  const char *v63; // rdx
  xpsrdr *v64; // rcx
  const char *v65; // r8
  int v66; // r9d
  int v67; // eax
  const char *v68; // rdx
  xpsrdr *v69; // rcx
  const char *v70; // r8
  int v71; // r9d
  __int128 *v72; // rbx
  unsigned __int64 v73; // rdi
  unsigned __int64 v74; // rsi
  int v75; // ecx
  const char *v76; // rdx
  __int64 v77; // rax
  int v78; // edx
  int v79; // edx
  int v80; // eax
  int v81; // edx
  const char *v82; // r8
  int v83; // r9d
  int v84; // r8d
  int v85; // eax
  int v86; // edx
  const char *v87; // r8
  int v88; // r9d
  __int64 *v89; // rcx
  __int64 v90; // rax
  int v91; // ebx
  int v92; // edx
  const char *v93; // r8
  int v94; // r9d
  int v95; // eax
  int v96; // edx
  const char *v97; // r8
  int v98; // r9d
  __int64 *v99; // rcx
  __int64 v100; // rax
  int v101; // ebx
  int v102; // edx
  const char *v103; // r8
  int v104; // r9d
  int v106; // [rsp+30h] [rbp-D0h] BYREF
  int v107; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v108; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v109; // [rsp+3Ch] [rbp-C4h] BYREF
  _QWORD v110[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v111[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v112; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v113; // [rsp+64h] [rbp-9Ch] BYREF
  int v114; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v115; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v116; // [rsp+70h] [rbp-90h] BYREF
  __int64 v117; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v118[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v119[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v120[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v121[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v122; // [rsp+D0h] [rbp-30h]
  _QWORD v123[3]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v124[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v125; // [rsp+108h] [rbp+8h] BYREF
  _QWORD *v126; // [rsp+118h] [rbp+18h]
  __int128 v127; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v128[12]; // [rsp+130h] [rbp+30h]
  xpsrdr *v129[2]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD *v130; // [rsp+150h] [rbp+50h]

  v122 = a2;
  v117 = a1;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v118);
  v106 = 0;
  v6 = *(__int64 **)(v5 + 16);
  v7 = *v6;
  *(_QWORD *)&v125 = 0;
  *((_QWORD *)&v125 + 1) = &v106;
  v126 = v118;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v7 + 80))(v6, &v125);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v125);
  if ( v106 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v106, v9, v10, v11);
  if ( v8 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v8, v9, v10, v11);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v110);
  v106 = 0;
  v12 = *(_QWORD *)v118[0];
  *(_QWORD *)&v125 = 0;
  *((_QWORD *)&v125 + 1) = &v106;
  v126 = v110;
  v13 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(v12 + 136))(v118[0], &v125);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v125);
  if ( v106 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v106, v14, v15, v16);
  if ( v13 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
  v112 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a3 + 48))(*a3, &v112);
  if ( v17 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v17, v18, v19, v20);
  (*(void (__fastcall **)(_QWORD, bool))(*(_QWORD *)v110[0] + 24LL))(v110[0], v112 == 2);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v120);
  v106 = 0;
  v21 = *a3;
  v22 = **a3;
  *(_QWORD *)&v125 = 0;
  *((_QWORD *)&v125 + 1) = &v106;
  v126 = v120;
  v23 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v22 + 40))(v21, &v125);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v125);
  if ( v106 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v106, v24, v25, v26);
  if ( v23 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v23, v24, v25, v26);
  (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v110[0] + 32LL))(v110[0], 0);
  std::vector<CCoordinate>::vector<CCoordinate>(v121, v27);
  std::vector<CCoordinate>::vector<CCoordinate>(v124, v28);
  std::vector<CCoordinate>::vector<CCoordinate>(v123, v29);
  v113 = 0;
  v30 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v120[0] + 24LL))(v120[0], &v113);
  if ( v30 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v30, v31, v32, v33);
  v34 = 1;
  v35 = 0;
LABEL_18:
  if ( v35 < v113 )
  {
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v111);
    LODWORD(v129[0]) = 0;
    v36 = *(_QWORD *)v120[0];
    *(_QWORD *)&v125 = 0;
    *((_QWORD *)&v125 + 1) = v129;
    v126 = v111;
    v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(v36 + 32))(v120[0], (unsigned int)v35, &v125);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v125);
    if ( SLODWORD(v129[0]) < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v129[0]), v38, v39, v40);
    if ( v37 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v37, v38, v39, v40);
    v117 = 0;
    v41 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v111[0] + 64LL))(v111[0], &v117);
    if ( v41 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v41, v42, v43, v44);
    v114 = 0;
    v45 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v111[0] + 96LL))(v111[0], &v114);
    if ( v45 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v45, v46, v47, v48);
    (*(void (__fastcall **)(_QWORD, unsigned __int64, bool))(*(_QWORD *)v110[0] + 40LL))(
      v110[0],
      _mm_unpacklo_ps((__m128)(unsigned int)v117, (__m128)HIDWORD(v117)).m128_u64[0],
      v114 == 0);
    v108 = 0;
    v49 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v111[0] + 112LL))(v111[0], &v108);
    if ( v49 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v49, v50, v51, v52);
    std::vector<enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011>::resize(v121, v108);
    std::vector<float>::resize(v124, v108);
    v109 = 0;
    v53 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v111[0] + 120LL))(v111[0], &v109);
    if ( v53 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v53, v54, v55, v56);
    std::vector<float>::resize(v123, v109);
    v115 = v108;
    v57 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, _QWORD))(*(_QWORD *)v111[0] + 40LL))(
            v111[0],
            &v115,
            v121[0]);
    if ( v57 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v57, (int)v58, v60, v61);
    if ( v115 != v108 )
      xpsrdr::ThrowLogicException(v59, v58, (int)v60);
    v116 = v108;
    v62 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, _QWORD))(*(_QWORD *)v111[0] + 48LL))(
            v111[0],
            &v116,
            v124[0]);
    if ( v62 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v62, (int)v63, v65, v66);
    if ( v116 != v108 )
      xpsrdr::ThrowLogicException(v64, v63, (int)v65);
    v107 = v109;
    v67 = (*(__int64 (__fastcall **)(_QWORD, int *, _QWORD))(*(_QWORD *)v111[0] + 32LL))(v111[0], &v107, v123[0]);
    if ( v67 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v67, (int)v68, v70, v71);
    if ( v107 != v109 )
      xpsrdr::ThrowLogicException(v69, v68, (int)v70);
    v72 = (__int128 *)v123[0];
    v73 = 0;
    v74 = (__int64)(v121[1] - v121[0]) >> 2;
    while ( 1 )
    {
      if ( v73 >= v74 )
      {
        v106 = 0;
        v80 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v111[0] + 80LL))(v111[0], &v106);
        if ( v80 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v80, v81, v82, v83);
        v84 = v106;
        if ( v106 && !v34 )
        {
          v34 = 1;
          (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v110[0] + 32LL))(v110[0], 0);
          v84 = v106;
        }
        (*(void (__fastcall **)(_QWORD, bool))(*(_QWORD *)v110[0] + 64LL))(v110[0], v84 != 0);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v111);
        ++v35;
        goto LABEL_18;
      }
      v75 = *(_DWORD *)(v124[0] + 4 * v73);
      if ( v34 != v75 )
      {
        v34 = *(_DWORD *)(v124[0] + 4 * v73);
        (*(void (__fastcall **)(_QWORD, bool))(*(_QWORD *)v110[0] + 32LL))(v110[0], v75 == 0);
      }
      v76 = (const char *)*(unsigned int *)(v121[0] + 4 * v73);
      if ( *(_DWORD *)(v121[0] + 4 * v73) == 1
        || *(_DWORD *)(v121[0] + 4 * v73) == 2
        || *(_DWORD *)(v121[0] + 4 * v73) == 3
        || *(_DWORD *)(v121[0] + 4 * v73) == 4 )
      {
        break;
      }
      switch ( *(_DWORD *)(v121[0] + 4 * v73) )
      {
        case 5:
          v127 = *v72;
          *(_QWORD *)v128 = *((_QWORD *)v72 + 2);
          (*(void (__fastcall **)(_QWORD, __int128 *, __int64))(*(_QWORD *)v110[0] + 56LL))(v110[0], &v127, 1);
          v77 = 24;
          break;
        case 6:
          v129[0] = *(xpsrdr **)v72;
          (*(void (__fastcall **)(_QWORD, xpsrdr **, __int64))(*(_QWORD *)v110[0] + 48LL))(v110[0], v129, 1);
          v77 = 8;
          break;
        case 7:
          *(_OWORD *)v129 = *v72;
          (*(void (__fastcall **)(_QWORD, xpsrdr **))(*(_QWORD *)v110[0] + 96LL))(v110[0], v129);
          v77 = 16;
          break;
        default:
          xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(*(_DWORD *)(v121[0] + 4 * v73) - 6), v76, (int)v70);
      }
LABEL_51:
      ++v73;
      v72 = (__int128 *)((char *)v72 + v77);
    }
    *(_QWORD *)&v128[4] = 0;
    v127 = *v72;
    *(_DWORD *)v128 = *((_DWORD *)v72 + 4);
    v78 = (_DWORD)v76 - 1;
    if ( v78 )
    {
      v79 = v78 - 1;
      if ( v79 )
      {
        *(_QWORD *)&v128[4] = v79 == 1;
LABEL_50:
        (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v110[0] + 112LL))(v110[0], &v127);
        v77 = 20;
        goto LABEL_51;
      }
    }
    else
    {
      *(_DWORD *)&v128[4] = 1;
    }
    *(_DWORD *)&v128[8] = 1;
    goto LABEL_50;
  }
  v85 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v110[0] + 72LL))(v110[0]);
  if ( v85 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v85, v86, v87, v88);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v119);
  v107 = 0;
  v89 = *a3;
  v90 = **a3;
  *(_QWORD *)&v125 = 0;
  *((_QWORD *)&v125 + 1) = &v107;
  v126 = v119;
  v91 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v90 + 64))(v89, &v125);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v125);
  if ( v107 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v107, v92, v93, v94);
  if ( v91 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v91, v92, v93, v94);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(v119) )
  {
    *(_OWORD *)v129 = 0;
    v130 = 0;
    v95 = (*(__int64 (__fastcall **)(_QWORD, xpsrdr **))(*(_QWORD *)v119[0] + 40LL))(v119[0], v129);
    if ( v95 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v95, v96, v97, v98);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v111);
    v107 = 0;
    v99 = *(__int64 **)(v122 + 16);
    v100 = *v99;
    *(_QWORD *)&v127 = 0;
    *((_QWORD *)&v127 + 1) = &v107;
    *(_QWORD *)v128 = v111;
    v125 = *(_OWORD *)v129;
    v126 = v130;
    v101 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int128 *, __int128 *))(v100 + 72))(
             v99,
             v118[0],
             &v125,
             &v127);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v127);
    if ( v107 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v107, v102, v103, v104);
    if ( v101 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v101, v102, v103, v104);
    std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(a1, v111);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v111);
  }
  else
  {
    std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(a1, v118);
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v119);
  std::vector<tagRGBQUAD>::_Tidy(v123);
  std::vector<tagRGBQUAD>::_Tidy(v124);
  std::vector<tagRGBQUAD>::_Tidy(v121);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v120);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v110);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v118);
  return a1;
}

```

## disassembly

```asm
0x18003b810  mov     [rsp-8+arg_18], rbx
0x18003b815  push    rbp
0x18003b816  push    rsi
0x18003b817  push    rdi
0x18003b818  push    r12
0x18003b81a  push    r13
0x18003b81c  push    r14
0x18003b81e  push    r15
0x18003b820  lea     rbp, [rsp-60h]
0x18003b825  sub     rsp, 160h
0x18003b82c  mov     rax, cs:__security_cookie
0x18003b833  xor     rax, rsp
0x18003b836  mov     [rbp+90h+var_38], rax
0x18003b83a  mov     r13, r8
0x18003b83d  mov     [rbp+90h+var_C0], rdx
0x18003b841  mov     r12, rcx
0x18003b844  mov     [rsp+190h+var_118], rcx
0x18003b849  xor     esi, esi
0x18003b84b  lea     rcx, [rbp+90h+var_110]
0x18003b84f  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003b854  nop
0x18003b855  mov     dword ptr [rsp+190h+var_160], esi
0x18003b859  mov     rcx, [rdx+10h]
0x18003b85d  mov     rax, [rcx]
0x18003b860  mov     qword ptr [rbp+90h+var_88], rsi
0x18003b864  lea     rdx, [rsp+190h+var_160]
0x18003b869  mov     qword ptr [rbp+90h+var_88+8], rdx
0x18003b86d  lea     rdx, [rbp+90h+var_110]
0x18003b871  mov     [rbp+90h+var_78], rdx
0x18003b875  lea     rdx, [rbp+90h+var_88]
0x18003b879  mov     rax, [rax+50h]
0x18003b87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b882  mov     ebx, eax
0x18003b884  lea     rcx, [rbp+90h+var_88]
0x18003b888  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003b88d  mov     ecx, dword ptr [rsp+190h+var_160]; this
0x18003b891  test    ecx, ecx
0x18003b893  jns     short loc_18003B89B
0x18003b895  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003b89b  test    ebx, ebx
0x18003b89d  jns     short loc_18003B8A7
0x18003b89f  mov     ecx, ebx; this
0x18003b8a1  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003b8a7  lea     rcx, [rsp+190h+var_150]
0x18003b8ac  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003b8b1  nop
0x18003b8b2  mov     dword ptr [rsp+190h+var_160], esi
0x18003b8b6  mov     rcx, [rbp+90h+var_110]
0x18003b8ba  mov     rax, [rcx]
0x18003b8bd  mov     qword ptr [rbp+90h+var_88], rsi
0x18003b8c1  lea     rdx, [rsp+190h+var_160]
0x18003b8c6  mov     qword ptr [rbp+90h+var_88+8], rdx
0x18003b8ca  lea     rdx, [rsp+190h+var_150]
0x18003b8cf  mov     [rbp+90h+var_78], rdx
0x18003b8d3  lea     rdx, [rbp+90h+var_88]
0x18003b8d7  mov     rax, [rax+88h]
0x18003b8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8e3  mov     ebx, eax
0x18003b8e5  lea     rcx, [rbp+90h+var_88]
0x18003b8e9  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003b8ee  mov     ecx, dword ptr [rsp+190h+var_160]; this
0x18003b8f2  test    ecx, ecx
0x18003b8f4  jns     short loc_18003B8FC
0x18003b8f6  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003b8fc  test    ebx, ebx
0x18003b8fe  jns     short loc_18003B908
0x18003b900  mov     ecx, ebx; this
0x18003b902  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003b908  mov     [rsp+190h+var_130], esi
0x18003b90c  mov     rcx, [r13+0]
0x18003b910  mov     rax, [rcx]
0x18003b913  lea     rdx, [rsp+190h+var_130]
0x18003b918  mov     rax, [rax+30h]
0x18003b91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b921  test    eax, eax
0x18003b923  jns     short loc_18003B92D
0x18003b925  mov     ecx, eax; this
0x18003b927  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003b92d  mov     rcx, [rsp+190h+var_150]
0x18003b932  mov     rax, [rcx]
0x18003b935  mov     edx, esi
0x18003b937  cmp     [rsp+190h+var_130], 2
0x18003b93c  setz    dl
0x18003b93f  mov     rax, [rax+18h]
0x18003b943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b948  lea     rcx, [rbp+90h+var_F0]
0x18003b94c  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003b951  nop
0x18003b952  mov     dword ptr [rsp+190h+var_160], esi
0x18003b956  mov     rcx, [r13+0]
0x18003b95a  mov     rax, [rcx]
0x18003b95d  mov     qword ptr [rbp+90h+var_88], rsi
0x18003b961  lea     rdx, [rsp+190h+var_160]
0x18003b966  mov     qword ptr [rbp+90h+var_88+8], rdx
0x18003b96a  lea     rdx, [rbp+90h+var_F0]
0x18003b96e  mov     [rbp+90h+var_78], rdx
0x18003b972  lea     rdx, [rbp+90h+var_88]
0x18003b976  mov     rax, [rax+28h]
0x18003b97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b97f  mov     ebx, eax
0x18003b981  lea     rcx, [rbp+90h+var_88]
0x18003b985  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003b98a  mov     ecx, dword ptr [rsp+190h+var_160]; this
0x18003b98e  test    ecx, ecx
0x18003b990  jns     short loc_18003B998
0x18003b992  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003b998  test    ebx, ebx
0x18003b99a  jns     short loc_18003B9A4
0x18003b99c  mov     ecx, ebx; this
0x18003b99e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003b9a4  mov     rcx, [rsp+190h+var_150]
0x18003b9a9  mov     rax, [rcx]
0x18003b9ac  xor     edx, edx
0x18003b9ae  mov     rax, [rax+20h]
0x18003b9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9b7  lea     rcx, [rbp+90h+var_E0]
0x18003b9bb  call    ??0?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::vector<CCoordinate>(void)
0x18003b9c0  nop
0x18003b9c1  lea     rcx, [rbp+90h+var_A0]
0x18003b9c5  call    ??0?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::vector<CCoordinate>(void)
0x18003b9ca  nop
0x18003b9cb  lea     rcx, [rbp+90h+var_B8]
0x18003b9cf  call    ??0?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::vector<CCoordinate>(void)
0x18003b9d4  nop
0x18003b9d5  mov     [rsp+190h+var_12C], esi
0x18003b9d9  mov     rcx, [rbp+90h+var_F0]
0x18003b9dd  mov     rax, [rcx]
0x18003b9e0  lea     rdx, [rsp+190h+var_12C]
0x18003b9e5  mov     rax, [rax+18h]
0x18003b9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9ee  test    eax, eax
0x18003b9f0  jns     short loc_18003B9FA
0x18003b9f2  mov     ecx, eax; this
0x18003b9f4  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003b9fa  mov     r14d, 1
0x18003ba00  mov     r15, rsi
0x18003ba03  mov     eax, [rsp+190h+var_12C]
0x18003ba07  cmp     r15, rax
0x18003ba0a  jnb     loc_18003BE40
0x18003ba10  lea     rcx, [rsp+190h+var_140]
0x18003ba15  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003ba1a  nop
0x18003ba1b  mov     dword ptr [rbp+90h+var_50], esi
0x18003ba1e  mov     rcx, [rbp+90h+var_F0]
0x18003ba22  mov     rax, [rcx]
0x18003ba25  mov     qword ptr [rbp+90h+var_88], rsi
0x18003ba29  lea     rdx, [rbp+90h+var_50]
0x18003ba2d  mov     qword ptr [rbp+90h+var_88+8], rdx
0x18003ba31  lea     rdx, [rsp+190h+var_140]
0x18003ba36  mov     [rbp+90h+var_78], rdx
0x18003ba3a  mov     edx, r15d
0x18003ba3d  lea     r8, [rbp+90h+var_88]
0x18003ba41  mov     rax, [rax+20h]
0x18003ba45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba4a  mov     ebx, eax
0x18003ba4c  lea     rcx, [rbp+90h+var_88]
0x18003ba50  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003ba55  mov     ecx, dword ptr [rbp+90h+var_50]; this
0x18003ba58  test    ecx, ecx
0x18003ba5a  js      loc_18003BE3A
0x18003ba60  test    ebx, ebx
0x18003ba62  js      loc_18003BE32
0x18003ba68  xor     eax, eax
0x18003ba6a  mov     [rsp+190h+var_118], rax
0x18003ba6f  mov     rcx, [rsp+190h+var_140]
0x18003ba74  mov     rax, [rcx]
0x18003ba77  lea     rdx, [rsp+190h+var_118]
0x18003ba7c  mov     rax, [rax+40h]
0x18003ba80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba85  test    eax, eax
0x18003ba87  js      loc_18003BE2A
0x18003ba8d  mov     [rsp+190h+var_128], esi
0x18003ba91  mov     rcx, [rsp+190h+var_140]
0x18003ba96  mov     rax, [rcx]
0x18003ba99  lea     rdx, [rsp+190h+var_128]
0x18003ba9e  mov     rax, [rax+60h]
0x18003baa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003baa7  test    eax, eax
0x18003baa9  js      loc_18003BE22
0x18003baaf  movss   xmm1, dword ptr [rsp+190h+var_118]
0x18003bab5  movss   xmm0, dword ptr [rsp+190h+var_118+4]
0x18003babb  mov     rcx, [rsp+190h+var_150]
0x18003bac0  mov     rax, [rcx]
0x18003bac3  mov     r8d, esi
0x18003bac6  cmp     [rsp+190h+var_128], esi
0x18003baca  setz    r8b
0x18003bace  unpcklps xmm1, xmm0
0x18003bad1  movq    rdx, xmm1
0x18003bad6  mov     rax, [rax+28h]
0x18003bada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003badf  mov     [rsp+190h+var_158], esi
0x18003bae3  mov     rcx, [rsp+190h+var_140]
0x18003bae8  mov     rax, [rcx]
0x18003baeb  lea     rdx, [rsp+190h+var_158]
0x18003baf0  mov     rax, [rax+70h]
0x18003baf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003baf9  test    eax, eax
0x18003bafb  js      loc_18003BE1A
0x18003bb01  mov     edx, [rsp+190h+var_158]
0x18003bb05  lea     rcx, [rbp+90h+var_E0]
0x18003bb09  call    ?resize@?$vector@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011@@V?$allocator@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011@@@std@@@std@@QEAAX_K@Z; std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0011>::resize(unsigned __int64)
0x18003bb0e  mov     edx, [rsp+190h+var_158]
0x18003bb12  lea     rcx, [rbp+90h+var_A0]
0x18003bb16  call    ?resize@?$vector@MV?$allocator@M@std@@@std@@QEAAX_K@Z; std::vector<float>::resize(unsigned __int64)
0x18003bb1b  mov     [rsp+190h+var_154], esi
0x18003bb1f  mov     rcx, [rsp+190h+var_140]
0x18003bb24  mov     rax, [rcx]
0x18003bb27  lea     rdx, [rsp+190h+var_154]
0x18003bb2c  mov     rax, [rax+78h]
0x18003bb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb35  test    eax, eax
0x18003bb37  js      loc_18003BE12
0x18003bb3d  mov     edx, [rsp+190h+var_154]
0x18003bb41  lea     rcx, [rbp+90h+var_B8]
0x18003bb45  call    ?resize@?$vector@MV?$allocator@M@std@@@std@@QEAAX_K@Z; std::vector<float>::resize(unsigned __int64)
0x18003bb4a  mov     eax, [rsp+190h+var_158]
0x18003bb4e  mov     [rsp+190h+var_124], eax
0x18003bb52  mov     rcx, [rsp+190h+var_140]
0x18003bb57  mov     rax, [rcx]
0x18003bb5a  mov     r8, [rbp+90h+var_E0]
0x18003bb5e  lea     rdx, [rsp+190h+var_124]
0x18003bb63  mov     rax, [rax+28h]
0x18003bb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb6c  test    eax, eax
0x18003bb6e  js      loc_18003BE0A
0x18003bb74  mov     eax, [rsp+190h+var_158]
0x18003bb78  cmp     [rsp+190h+var_124], eax
0x18003bb7c  jnz     loc_18003BE04
0x18003bb82  mov     [rsp+190h+var_120], eax
0x18003bb86  mov     rcx, [rsp+190h+var_140]
0x18003bb8b  mov     rax, [rcx]
0x18003bb8e  mov     r8, [rbp+90h+var_A0]
0x18003bb92  lea     rdx, [rsp+190h+var_120]
0x18003bb97  mov     rax, [rax+30h]
0x18003bb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bba0  test    eax, eax
0x18003bba2  js      loc_18003BDFC
0x18003bba8  mov     eax, [rsp+190h+var_158]
0x18003bbac  cmp     [rsp+190h+var_120], eax
0x18003bbb0  jnz     loc_18003BDF6
0x18003bbb6  mov     eax, [rsp+190h+var_154]
0x18003bbba  mov     dword ptr [rsp+190h+var_160+4], eax
0x18003bbbe  mov     rcx, [rsp+190h+var_140]
0x18003bbc3  mov     rax, [rcx]
0x18003bbc6  mov     r8, [rbp+90h+var_B8]
0x18003bbca  lea     rdx, [rsp+190h+var_160+4]
0x18003bbcf  mov     rax, [rax+20h]
0x18003bbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbd8  test    eax, eax
0x18003bbda  js      loc_18003BDEE
0x18003bbe0  mov     eax, [rsp+190h+var_154]
0x18003bbe4  cmp     dword ptr [rsp+190h+var_160+4], eax
0x18003bbe8  jnz     loc_18003BDE8
0x18003bbee  mov     rbx, [rbp+90h+var_B8]
0x18003bbf2  mov     rdi, rsi
0x18003bbf5  mov     rsi, [rbp+90h+var_D8]
0x18003bbf9  sub     rsi, [rbp+90h+var_E0]
0x18003bbfd  sar     rsi, 2
0x18003bc01  cmp     rdi, rsi
0x18003bc04  jnb     loc_18003BD63
0x18003bc0a  mov     rax, [rbp+90h+var_A0]
0x18003bc0e  mov     ecx, [rax+rdi*4]
0x18003bc11  cmp     r14d, ecx
0x18003bc14  jz      short loc_18003BC37
0x18003bc16  mov     r14d, ecx
0x18003bc19  test    ecx, ecx
0x18003bc1b  mov     rcx, [rsp+190h+var_150]
0x18003bc20  mov     rax, [rcx]
0x18003bc23  mov     rax, [rax+20h]
0x18003bc27  jz      short loc_18003BC2D
0x18003bc29  xor     edx, edx
0x18003bc2b  jmp     short loc_18003BC32
0x18003bc2d  mov     edx, 1
0x18003bc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc37  mov     rax, [rbp+90h+var_E0]
0x18003bc3b  mov     edx, [rax+rdi*4]; char *
0x18003bc3e  mov     ecx, edx
0x18003bc40  sub     ecx, 1
0x18003bc43  jz      loc_18003BCFE
0x18003bc49  sub     ecx, 1
0x18003bc4c  jz      loc_18003BCFE
0x18003bc52  sub     ecx, 1
0x18003bc55  jz      loc_18003BCFE
0x18003bc5b  sub     ecx, 1
0x18003bc5e  jz      loc_18003BCFE
0x18003bc64  sub     ecx, 1
0x18003bc67  jz      short loc_18003BCCB
0x18003bc69  sub     ecx, 1; this
0x18003bc6c  jz      short loc_18003BC9D
0x18003bc6e  cmp     ecx, 1
0x18003bc71  jnz     loc_18003BDDA
0x18003bc77  movups  xmm0, xmmword ptr [rbx]
0x18003bc7a  movups  xmmword ptr [rbp+90h+var_50], xmm0
0x18003bc7e  mov     rcx, [rsp+190h+var_150]
0x18003bc83  mov     rax, [rcx]
0x18003bc86  lea     rdx, [rbp+90h+var_50]
0x18003bc8a  mov     rax, [rax+60h]
0x18003bc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc93  mov     eax, 10h
0x18003bc98  jmp     loc_18003BD58
  ... truncated ...
```
